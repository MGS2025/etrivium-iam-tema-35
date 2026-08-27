# Tema 35 — Casos Prácticos

> **Título oficial**: Internet: arquitectura de red. Origen, evolución y estado actual. Principales servicios. Protocolos HTTP, HTTPS y SSL/TLS.
>
> **Formato**: 3 casos prácticos sobre supuestos reales del Ayuntamiento de Madrid. Cada caso suma **10 puntos**.
> **Nivel**: C1 — Técnico Auxiliar TIC, Ayuntamiento de Madrid

Los tres casos giran sobre el supuesto de referencia del tema (ver tema-35-contenido.md, «Convenciones»): la **sede electrónica municipal**. El **Caso 1** trabaja la **publicación de un servicio nuevo en internet** (nombres, direccionamiento, HTTPS y certificados); el **Caso 2**, el **diagnóstico por capas de una incidencia** real, con lectura de trazas y códigos de estado; y el **Caso 3**, los **servicios de soporte**: correo suplantado y transferencia de ficheros con datos personales.

---

## Caso 1 — Publicación de un nuevo trámite en la sede electrónica

### Enunciado

El Ayuntamiento va a publicar un **nuevo trámite de solicitud de ayudas** en la dirección `ayudas.sede.madrid.es`. El equipo de proyecto plantea la siguiente configuración inicial:

- El nombre se dará de alta en la zona `madrid.es`, servida por **un único servidor DNS autoritativo** alojado en el CPD del IAM.
- El servicio se publicará **solo en IPv4**, «porque IPv6 todavía no lo usa nadie en España».
- Se atenderá en **HTTP por el puerto 80 y en HTTPS por el 443**, dejando ambos abiertos «para no dejar fuera a nadie».
- Se contratará un **certificado de un año de validez** a una autoridad de certificación pública, con renovación manual anotada en la agenda del responsable.
- La aplicación guardará la sesión en una **cookie sin atributos**, y devolverá las páginas con datos del solicitante **sin cabeceras de caché**.
- El sistema ha sido categorizado **MEDIA** conforme al ENS.

Se pide un informe técnico previo a la puesta en producción.

### Cuestiones

**Cuestión 1 — Nombres y direccionamiento (3 puntos).** Analice las decisiones sobre **DNS** y sobre el **direccionamiento**, indicando qué riesgos introducen y qué configuración propondría en su lugar.

**Cuestión 2 — Transporte seguro (3 puntos).** Valore la decisión de mantener HTTP y HTTPS abiertos y la del certificado. Indique **qué versiones de TLS** deben admitirse en 2026 y **por qué el certificado propuesto no es viable**.

**Cuestión 3 — Configuración de la aplicación (2 puntos).** Corrija la configuración de la **cookie de sesión** y de la **caché**, justificando cada atributo por la amenaza que mitiga.

**Cuestión 4 — Respaldo normativo (2 puntos).** Cite las **medidas del ENS** y los **preceptos legales** que amparan cada una de las correcciones anteriores.

### Solución orientativa

- **C1**: (§2.2.2, §2.2.3)

| Decisión del proyecto | Riesgo | Propuesta |
|---|---|---|
| **Un solo servidor DNS autoritativo** | **Punto único de fallo**: si cae, el servicio no se cae técnicamente, pero **nadie lo encuentra**, con efecto idéntico a una caída total | **Al menos dos** servidores autoritativos, en **redes y emplazamientos distintos** (uno primario y uno o varios secundarios por transferencia de zona restringida) |
| Zona sin protección adicional | Suplantación de respuestas y **envenenamiento de caché** | **DNSSEC** en la zona; **registro CAA** para limitar qué AC puede emitir certificados; vigilancia de la **caducidad del dominio** y bloqueo en el registrador |
| **Publicación solo en IPv4** | Penaliza el acceso desde redes móviles con **CGNAT** y contradice la orientación de neutralidad tecnológica del ENI | **Doble pila** IPv4/IPv6, con las **reglas de cortafuegos duplicadas** en ambos protocolos: una regla que solo cubre IPv4 deja abierta la puerta IPv6 |

  Se valora que el aspirante **rebata con datos** el argumento «IPv6 no lo usa nadie»: la media mundial superó el **50 %** el 28-3-2026, y aunque España esté en torno al **10 %**, la publicación en doble pila **no perjudica** a los usuarios IPv4 y prepara el servicio para la evolución.

- **C2**: (§5.1, §5.2)
  - **HTTP y HTTPS abiertos a la vez es un error.** El puerto 80 debe mantenerse abierto **solo** para **redirigir con un 301** a HTTPS, nunca para servir contenido. Y la redirección **no basta por sí sola**: la primera petición viaja en claro y es interceptable (*SSL stripping*), por lo que hay que añadir **HSTS** con `includeSubDomains` y, si el dominio lo permite, solicitar la **precarga**, que aplica la protección desde la primera visita.
  - **Versiones**: admitir **TLS 1.2 y TLS 1.3**, con preferencia por 1.3; **deshabilitar SSL 2.0 y 3.0** (prohibidos por los RFC 6176 y 7568) y **TLS 1.0 y 1.1** (obsoletos, RFC 8996). Los algoritmos y parámetros deben ser los **autorizados por el CCN** (guía **CCN-STIC-807**), que es la formulación que emplea el propio ENS.
  - **El certificado de un año no es viable**: desde el **15 de marzo de 2026** el máximo admitido por el CA/Browser Forum es de **200 días**, y bajará a **100 días en 2027** y a **47 días en 2029**. La consecuencia organizativa es la parte importante: **la renovación manual deja de ser sostenible**, y hay que implantar **renovación automatizada** (ACME), **inventario de certificados** con responsable asignado y alertas anticipadas. La caducidad de un certificado es una causa banal y frecuente de caída de servicios públicos.
  - Añadir **grapado OCSP** o, mejor, asumir el modelo de **certificados de vida corta**, que es hacia donde se dirige el sector tras el apagado del OCSP de Let's Encrypt en agosto de 2025.

- **C3**: (§4.2.2)

| Elemento | Configuración correcta | Amenaza que mitiga |
|---|---|---|
| Cookie de sesión | **`Secure`** | Interceptación en tránsito: la cookie no se envía por HTTP |
| | **`HttpOnly`** | Robo del identificador mediante **secuencias de órdenes en sitios cruzados (XSS)** |
| | **`SameSite=Lax`** o `Strict` | **Falsificación de petición en sitios cruzados (CSRF)** |
| | Identificador **aleatorio, largo y renovado tras el acceso**, con caducidad por inactividad | Predicción del identificador y **fijación de sesión** |
| Caché de páginas con datos del solicitante | **`Cache-Control: no-store, private`** | Que la respuesta quede almacenada en el navegador de un **puesto compartido**. Ojo: `no-cache` **no** vale, porque permite almacenar y solo obliga a revalidar |

  Se valora añadir las **cabeceras de seguridad** mínimas: `Content-Security-Policy`, `X-Content-Type-Options: nosniff`, `X-Frame-Options` o `frame-ancestors`, y `Referrer-Policy`.

- **C4**: (§6.1.1)

| Corrección | Respaldo |
|---|---|
| Cifrado del canal | **`mp.com.2`** (protección de la confidencialidad): desde nivel MEDIO exige **+R1**, algoritmos y parámetros **autorizados por el CCN** |
| Autenticación del servidor e integridad del canal | **`mp.com.3`** (protección de la integridad y de la autenticidad): en nivel MEDIO, **+R1 +R2** |
| Auditoría del servicio web y prevención de XSS y escalado de privilegios | **`mp.s.2`**, exigible en **las tres categorías** con **[R1 o R2]** |
| Custodia de la clave privada del certificado | **`op.exp.10`** (protección de claves criptográficas) |
| Certificado de sede y comunicación segura | **Art. 38 de la Ley 40/2015** y **RD 203/2021** |
| Disponibilidad del servicio frente a denegación | **`mp.s.4`**, exigible desde nivel **MEDIO** de disponibilidad |
| Accesibilidad del nuevo trámite | **RD 1112/2018** y norma **UNE-EN 301 549**, con **declaración de accesibilidad** publicada |
| Tratamiento de datos personales del solicitante | **Art. 32 del RGPD** y **`mp.info.1`** |

### Criterios de evaluación

| Criterio | Puntos |
|---|---|
| Detecta el punto único de fallo del DNS y propone redundancia, DNSSEC y CAA | 1,5 |
| Argumenta la publicación en doble pila y advierte de la duplicación de reglas de cortafuegos | 1,5 |
| Explica que la redirección 301 no basta y propone HSTS con precarga | 1,0 |
| Fija correctamente las versiones de TLS admisibles y las prohibidas | 1,0 |
| Detecta la inviabilidad del certificado de un año y propone automatización de la renovación | 1,0 |
| Corrige la cookie con los tres atributos, asociando cada uno a su amenaza | 1,0 |
| Distingue `no-store` de `no-cache` | 1,0 |
| Cita correctamente `mp.com.2`, `mp.com.3` y `mp.s.2` | 1,0 |
| Cita el art. 38 de la Ley 40/2015 y el marco de accesibilidad y protección de datos | 1,0 |

---

## Caso 2 — Diagnóstico por capas de una incidencia en una oficina de distrito

### Enunciado

El **Centro de Atención a Usuarios** del IAM recibe, a lo largo de la misma mañana, tres avisos procedentes de una **Oficina de Atención a la Ciudadanía** de distrito:

- **Aviso 1**: «No se abre `sede.madrid.es`». En el puesto afectado, `ping 8.8.8.8` responde correctamente, pero `ping sede.madrid.es` devuelve «host desconocido». Desde el móvil del propio empleado, con datos móviles, la sede se abre sin problema.
- **Aviso 2**: en otro puesto, la sede **abre la portada**, pero al enviar el formulario de un trámite el navegador muestra **«502 Bad Gateway»**. Poco después, otros usuarios reciben **«503 Service Unavailable»**.
- **Aviso 3**: un tercer puesto muestra el aviso del navegador **«La conexión no es privada — el certificado no es válido»** al entrar en un servicio interno publicado por HTTPS. El empleado pregunta si puede «darle a continuar».

Además, el responsable de la oficina comenta que esa mañana **un proveedor conectó un portátil a una toma de red de la zona de público** para hacer una demostración.

### Cuestiones

**Cuestión 1 — Aviso 1 (3 puntos).** Determine **en qué capa** está el problema, razone la deducción a partir de las pruebas descritas y proponga **dos comprobaciones adicionales** y la causa más probable, teniendo en cuenta el dato del proveedor.

**Cuestión 2 — Aviso 2 (2,5 puntos).** Interprete los códigos **502** y **503**: quién los emite, qué significan y en qué se diferencian del 500 y del 504.

**Cuestión 3 — Aviso 3 (2,5 puntos).** Explique **qué comprueba** un navegador al validar un certificado, enumere las causas posibles del aviso y responda a la pregunta del empleado.

**Cuestión 4 — Medida preventiva (2 puntos).** Proponga las medidas para que el incidente del portátil conectado a la toma de público no vuelva a producirse, con su respaldo en el ENS.

### Solución orientativa

- **C1**: (§2.1.2, §2.2.3, §3.2.2)
  - **Deducción por capas, de abajo arriba**: el `ping` a una **dirección IP** funciona, luego las capas **física, de enlace y de internet** están operativas y hay conectividad hasta un destino externo. Lo que falla es la **traducción del nombre**, que es un servicio de la **capa de aplicación**: el problema está en el **DNS**, no en la red. Que la sede sí abra desde el móvil —que usa el DNS del operador— **confirma** que el servicio publicado está bien y que el fallo es local.
  - **Comprobaciones adicionales**: (1) `nslookup sede.madrid.es` contra el **DNS corporativo** y después contra uno externo: si solo falla contra el corporativo, el fallo está en el resolutor de la organización; (2) `ipconfig /all` o `ip a` para ver **qué servidores DNS y qué pasarela** ha recibido el puesto y **de qué servidor DHCP** procede la concesión.
  - **Causa más probable**, unida al dato del proveedor: un **servidor DHCP no autorizado** en el portátil conectado a la toma de público, que ha entregado a los puestos una configuración con **DNS y pasarela falsos**. Es el escenario clásico: un DHCP no autorizado no solo rompe la resolución, sino que **puede convertir al atacante en intermediario** de todo el tráfico. Alternativas menos graves: caída del resolutor corporativo o error en la zona.

- **C2**: (§4.2.1)

| Código | Quién lo emite | Significado |
|---|---|---|
| **500 Internal Server Error** | La **aplicación** de origen | Error genérico no controlado dentro del propio servidor |
| **502 Bad Gateway** | Un **intermediario** (proxy inverso o balanceador) | El servidor de origen devolvió una respuesta **inválida** |
| **503 Service Unavailable** | El servidor o el intermediario | El servicio **no está disponible** temporalmente: sobrecarga o mantenimiento. Admite la cabecera `Retry-After` |
| **504 Gateway Timeout** | Un **intermediario** | El origen **no respondió a tiempo** |

  Lectura del caso: 502 seguido de 503 generalizado apunta a que **el servidor de aplicación de origen ha dejado de responder correctamente** y el proxy inverso ha pasado de recibir respuestas inválidas a declarar el servicio no disponible. Es un problema **del lado del servidor**, no del puesto, y procede escalarlo al equipo de la aplicación en lugar de intervenir en la oficina. Se valora señalar que **toda la familia 5xx es responsabilidad del servidor**, mientras que la **4xx** lo es del cliente.

- **C3**: (§5.1.2)
  - **Qué comprueba el navegador** al validar: (1) que la **firma** de cada eslabón sea correcta hasta llegar a una **AC raíz** de su almacén de confianza; (2) la **vigencia** (`notBefore`/`notAfter`); (3) que el nombre solicitado figure en la extensión **`subjectAltName`**; (4) las **restricciones básicas** (que las intermedias puedan actuar como AC); y (5) el **estado de revocación** (CRL, OCSP o grapado).
  - **Causas posibles** del aviso: certificado **caducado** —la más frecuente—; **nombre no incluido** en el SAN (por ejemplo, se accede por la IP o por un alias); certificado **autofirmado** o emitido por una **AC interna** no instalada en el almacén del puesto; **cadena incompleta** (falta la intermedia); **fecha del sistema** del puesto desajustada; o, en el peor caso, **interceptación** por un intermediario.
  - **Respuesta al empleado**: **no**. Aceptar el aviso anula precisamente la garantía que aporta TLS, que es saber que se está hablando con quien se cree. Procede **identificar la causa** —comprobando el certificado y la fecha del puesto— y corregirla: renovar el certificado, completar la cadena, distribuir la AC interna por directiva o corregir el nombre. Se valora relacionarlo con la mala práctica de «acostumbrar al usuario a aceptar avisos», que es la puerta de entrada de los ataques de intermediario.

- **C4**: (§3.2.2, §6.1.1)
  - **Medidas técnicas**: **DHCP snooping** en el conmutador de planta, admitiendo respuestas DHCP solo por los puertos declarados de confianza; **RA Guard** para el equivalente IPv6 (anuncios de encaminador falsos); **deshabilitar las tomas de red no utilizadas**; **autenticación de puerto 802.1X**; y **VLAN separada** para equipos ajenos al Ayuntamiento y para la zona de público.
  - **Medidas organizativas**: procedimiento de autorización previa para conectar equipos de terceros y registro de esas conexiones.
  - **Respaldo del ENS**: **`mp.com.4`**, «separación de flujos de información en la red», que exige segregar el tráfico y que las comunicaciones inalámbricas vayan en un segmento propio; **`mp.com.1`**, perímetro seguro; y **`mp.eq.4`**, otros dispositivos conectados a la red. Se valora citar también la dimensión de **trazabilidad** y la exigencia de **identificación única** de los usuarios.

### Criterios de evaluación

| Criterio | Puntos |
|---|---|
| Aísla el problema por capas y concluye que el fallo es de resolución de nombres, no de red | 1,5 |
| Propone comprobaciones pertinentes y relaciona la causa con el DHCP no autorizado | 1,5 |
| Interpreta correctamente 502 y 503 y los distingue de 500 y 504 | 1,5 |
| Concluye que la incidencia es del lado del servidor y procede escalarla | 1,0 |
| Enumera qué comprueba el navegador al validar el certificado | 1,5 |
| Responde correctamente que no debe aceptarse el aviso y razona por qué | 1,0 |
| Propone DHCP snooping, RA Guard, 802.1X y segmentación | 1,0 |
| Ancla las medidas en `mp.com.4` y `mp.com.1` | 1,0 |

---

## Caso 3 — Correo suplantado y envío de un fichero con datos personales

### Enunciado

Dos asuntos llegan el mismo día a la unidad TIC del Ayuntamiento:

**Asunto A.** Varias personas comunican que han recibido un correo aparentemente enviado desde `tesoreria@madrid.es` en el que se les reclama el pago urgente de una tasa mediante un enlace. El mensaje **no ha salido de los servidores municipales**. Al revisar la configuración del dominio se comprueba que:

- Existe un registro **SPF**, pero termina en `~all` (fallo blando).
- **No hay DKIM** configurado.
- Existe un registro **DMARC** con política `p=none`.

**Asunto B.** Un servicio del Ayuntamiento debe enviar cada noche a otro organismo un fichero con **datos identificativos y de contacto** de personas solicitantes de una ayuda. La propuesta del proveedor es publicar el fichero en un **servidor FTP anónimo** accesible desde internet, «porque es lo más sencillo y ya lo hacemos con otros clientes».

### Cuestiones

**Cuestión 1 — Análisis de la suplantación (3 puntos).** Explique **por qué el atacante ha podido enviar ese correo** pese a existir SPF y DMARC, y qué papel juega cada uno de los tres mecanismos.

**Cuestión 2 — Corrección propuesta (2,5 puntos).** Indique la configuración concreta que propondría para los tres mecanismos y **en qué orden** la desplegaría para no bloquear correo legítimo.

**Cuestión 3 — Transferencia del fichero (2,5 puntos).** Valore la propuesta del proveedor y proponga una alternativa, distinguiendo con precisión las opciones seguras disponibles.

**Cuestión 4 — Respaldo normativo (2 puntos).** Cite las medidas del ENS y la normativa de protección de datos aplicables a ambos asuntos.

### Solución orientativa

- **C1**: (§3.1.1)
  - La raíz del problema es estructural: **SMTP no autentica la cabecera `From`**, que es la que ve el destinatario. Cualquiera puede escribir ahí lo que quiera. Los tres mecanismos existen precisamente para tapar ese agujero, y cada uno hace una cosa distinta:

| Mecanismo | Qué hace | Por qué no bastó aquí |
|---|---|---|
| **SPF** | Publica **qué servidores** pueden enviar con el dominio; se comprueba contra la **envuelta** (`MAIL FROM`), no contra el `From` visible | Termina en **`~all`**, un fallo **blando**: el receptor puede aceptar el mensaje marcándolo, y además SPF **no protege el `From` que ve el usuario** |
| **DKIM** | **Firma criptográficamente** cabeceras y cuerpo con una clave cuya pública se publica en el DNS | **No está configurado**: no hay ninguna firma que validar |
| **DMARC** | Exige el **alineamiento** entre el `From` visible y lo validado por SPF o DKIM, y fija la **política** | Está en **`p=none`**: solo **observa e informa**, no pide ninguna acción al receptor |

  - Conclusión que se espera: **SPF y DKIM por sí solos no impiden el fraude**, porque validan la envuelta o la firma, no lo que ve el usuario; es **DMARC** quien exige la coherencia y quien dice qué hacer, y con `p=none` no dice nada.

- **C2**: (§3.1.1)
  1. **Inventariar todos los emisores legítimos** del dominio: servidores del Ayuntamiento, plataformas de notificación, herramientas de boletines, aplicaciones que envían avisos. Es el paso que se salta todo el mundo y el que provoca los bloqueos de correo legítimo.
  2. **Configurar DKIM** en todos ellos y publicar la clave pública en su selector.
  3. **Endurecer SPF** a **`-all`** (fallo duro), una vez comprobado que la lista de emisores está completa.
  4. **Escalar DMARC progresivamente**: mantener `p=none` recibiendo **informes agregados** unas semanas, pasar después a **`p=quarantine`** con porcentaje creciente y terminar en **`p=reject`**, que es el objetivo.
  5. Complementar con **MTA-STS** o DANE en el lado saliente y con filtrado antimalware y antispam en el entrante, además de **concienciación** del personal y de un canal para que la ciudadanía comunique correos sospechosos.

  Se valora expresamente el **orden**: endurecer la política antes de tener DKIM y el inventario de emisores es la causa más frecuente de que se pierda correo legítimo.

- **C3**: (§3.1.2)
  - **La propuesta es inaceptable** y hay que rechazarla razonadamente: un **FTP anónimo** no autentica a quien accede, y **FTP transmite credenciales y datos en claro**. Un fichero con datos personales expuesto así es una **violación de seguridad** en potencia.
  - **Alternativa propuesta**: **SFTP** —subsistema de **SSH**, puerto **22**— con **autenticación por par de claves** y no por contraseña, acceso **restringido por dirección de origen**, cuenta de servicio con **mínimo privilegio** confinada a su directorio, **registro** de cada transferencia y **cifrado del propio fichero** además del canal, de modo que el dato siga protegido en reposo en el destino.
  - **Precisión que se evalúa**: distinguir **SFTP** de **FTPS**. FTPS **es FTP** envuelto en TLS y conserva sus dos canales, con los problemas de cortafuegos del modo activo; **SFTP no tiene ninguna relación con FTP**, usa un solo canal y es la opción preferible. Alternativas igualmente válidas: **HTTPS** con API autenticada, o los servicios de intercambio de la **red SARA** y las plataformas de intermediación de datos, que además evitan tener que enviar el fichero.
  - Conviene además cuestionar el propio envío: si el organismo destinatario puede obtener el dato por **intermediación**, lo correcto es **no transferir el fichero**, aplicando minimización.

- **C4**: (§6.1.1)

| Asunto | Respaldo |
|---|---|
| Correo | **`mp.s.1`** — protección del correo electrónico, exigible en **las tres categorías**: protección de la información y de los **datos de encaminamiento**, y actuación frente a **correo no solicitado**, **código dañino** y **código móvil**, con normativa de uso y **concienciación** |
| Transferencia cifrada | **`mp.com.2`** (confidencialidad) y **`mp.com.3`** (integridad y autenticidad) del canal |
| Cifrado del fichero y del soporte | **`mp.si.2`** — criptografía en los soportes de información |
| Gestión de las claves SSH | **`op.exp.10`** — protección de claves criptográficas |
| Acceso de la cuenta de servicio | **`op.acc.4`** (proceso de gestión de derechos de acceso) y el **mínimo privilegio** del art. 20 del ENS |
| Datos personales | **Art. 5.1.f y art. 32 del RGPD** (seguridad del tratamiento), **`mp.info.1`** del ENS y, si hubiera exfiltración, la **notificación en 72 horas** de los arts. 33 y 34 del RGPD |
| Suplantación con perjuicio a la ciudadanía | Comunicación al **CCN-CERT** conforme a la gestión de ciberincidentes, y aviso público en los canales municipales |

### Criterios de evaluación

| Criterio | Puntos |
|---|---|
| Explica que SMTP no autentica el `From` y que ahí está la raíz del problema | 1,0 |
| Distingue con precisión qué hace SPF, qué DKIM y qué DMARC | 1,0 |
| Identifica que `~all` y `p=none` son la causa concreta de que no se bloqueara | 1,0 |
| Propone la configuración correcta y, sobre todo, el **orden** de despliegue | 1,5 |
| Advierte del riesgo de endurecer la política sin inventario de emisores | 1,0 |
| Rechaza el FTP anónimo con argumentos técnicos | 1,0 |
| Propone SFTP con claves y distingue correctamente SFTP de FTPS | 1,5 |
| Cita `mp.s.1`, `mp.com.2` y `mp.si.2` | 1,0 |
| Relaciona el caso con el RGPD y con la notificación de violaciones | 1,0 |
