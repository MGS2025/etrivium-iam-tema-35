# Tema 35 — Validación

> **Título oficial**: Internet: arquitectura de red. Origen, evolución y estado actual. Principales servicios. Protocolos HTTP, HTTPS y SSL/TLS.
>
> **Versión**: v1.0 — **Pendiente de validación por María, Ana y el IAM**
> **Fecha**: 2026-08-27

---

## 1. Cobertura del temario oficial

El enunciado oficial (BOAM 10.032, tema 35) enumera **cuatro materias**. Correspondencia con las secciones del contenido:

| Enunciado oficial | Sección | Estado |
|---|---|---|
| Internet: **arquitectura de red** | §2 | ✅ Completo |
| **Origen, evolución y estado actual** | §1 | ✅ Completo |
| **Principales servicios** | §3 | ✅ Completo |
| **Protocolos HTTP, HTTPS y SSL/TLS** | §4 y §5 | ✅ Completo |
| *(Añadido por el esqueleto de partida)* Seguridad y normativa en la Administración Pública | §6 | ✅ Completo |

El **esqueleto de partida** (`Test_Prompting/temas agosto/35.md`) se ha seguido **literalmente**: sus **seis bloques de primer nivel**, sus **doce subapartados** y sus **veintiún epígrafes** se corresponden uno a uno con la numeración `N`, `N.M` y `N.M.K` del contenido. **Es el primer esqueleto de la serie de agosto que encaja sin ajustes en los tres niveles de numeración**, a diferencia de lo ocurrido en los Temas 27 y 30.

## 2. Contenido teórico

- **6 secciones · 12 subsecciones · 21 epígrafes numerados** (numeración de tres niveles, coherente con el resto de la serie técnica).
- **≈ 18.600 palabras** medidas con `wc -w`, en la parte alta del rango de la serie (T31 ≈ 17.600, T28 ≈ 18.900, T29 ≈ 21.200, T32 ≈ 25.000).
- **4 tipos de callout**: `[DATO CLAVE EXAMEN]`, `[EJERCICIO RESUELTO]`, `[EJEMPLO AYTO MADRID]` y `[REFERENCIA CRUZADA]`.
- **Caso de referencia transversal**: la sede electrónica municipal `sede.madrid.es`, que atraviesa las seis secciones y enlaza con los tres casos prácticos.
- **Sin fragmentos de código**, como en T26, T28, T29, T30, T31 y T32. Decisión deliberada: el enunciado no menciona ningún lenguaje y lo memorizable son **puertos, números de RFC, códigos de estado, fechas y siglas**, concentrados en tablas y en los diagramas D4, D8, D14 y D17. Sí se incluyen **tres bloques literales no ejecutables** —la descomposición de una URL, un mensaje HTTP de petición y otro de respuesta, y una suite de cifrado desmenuzada— porque son objeto directo de pregunta.
- Cierre con un bloque de **«los siete datos que no se pueden fallar»**, no numerado, a modo de resumen memorístico.

## 3. Fuentes

- **Tier 1**: 60 referencias (normativa española y europea, más las especificaciones del IETF, ISO/IEC, W3C, IEEE y NIST).
- **Tier 2**: 18 referencias de informes y estadísticas oficiales, todas fechadas.
- **Tier 3**: 3 referencias de contexto municipal.
- **Verificación contra fuente primaria** (no de memoria ni de fuentes secundarias):
  - **RFC**: se descargó el **índice oficial del RFC Editor** (`rfc-index.txt`) y se comprobaron uno a uno **número, título, fecha, estado y relaciones de obsolescencia** de los RFC citados. De ahí salieron los tres hallazgos que se detallan en el punto 8.
  - **ENS**: PDF oficial del BOE (`BOE-A-2022-7191`) extraído con `pdftotext -layout`. De ahí proceden, literales, las denominaciones y las tablas de aplicación de `mp.com.1` a `mp.com.4` y de `mp.s.1` a `mp.s.4`.
  - **Cifras del estado actual**: verificadas en el organismo que las publica, con fecha (UIT, Google IPv6, CIDR Report, W3Techs, Dominios.es, CA/Browser Forum, ESPANIX y DE-CIX).

## 4. Test (60 preguntas)

- **60 preguntas** de 3 opciones (A/B/C), formato oficial de la oposición, con penalización de **1/3** en el motor de corrección.
- **Distribución de la respuesta correcta: 20 A / 20 B / 20 C**, conseguida **a la primera** por haber fijado la secuencia de letras **antes** de redactar (lección aprendida en T23) y verificada por script.
- Reparto por materia: P1-P11 origen, evolución, gobernanza y RFC · P12-P26 arquitectura, direccionamiento y DNS · P27-P37 servicios (correo, ficheros, SSH y DHCP) · P38-P48 HTTP · P49-P58 SSL/TLS y HTTPS · P59-P60 normativa en la Administración.
- Verificación automática: 60 preguntas, 3 opciones únicas por pregunta, **coincidencia exacta** entre el texto de la opción correcta y el de la solución, y referencia a epígrafe y fuente en las 60.

## 5. Casos prácticos (3)

Los tres se sitúan en el Ayuntamiento de Madrid y comparten el sistema de referencia del tema:

1. **Publicación de un nuevo trámite en la sede** (§2, §4, §5 y §6): DNS redundante, DNSSEC y CAA, publicación en doble pila, HTTPS con HSTS, versiones de TLS admisibles, inviabilidad de un certificado de un año y configuración de cookies y caché.
2. **Diagnóstico por capas de una incidencia en una oficina de distrito** (§2, §3 y §4): aislamiento del fallo de resolución de nombres, interpretación de los códigos 502, 503, 500 y 504, validación de certificados y respuesta al usuario que quiere «continuar», y prevención del servidor DHCP no autorizado.
3. **Correo suplantado y envío de un fichero con datos personales** (§3 y §6): por qué SPF y DMARC no bastaron, orden correcto de despliegue de SPF, DKIM y DMARC, y sustitución de un FTP anónimo por SFTP con claves.

Cada caso suma **10 puntos** repartidos en cuatro cuestiones, con solución orientativa y tabla de criterios de evaluación.

## 6. Diagramas (18 SVG)

- **18 diagramas SVG inline**, sin dependencias externas, con `role="img"` y `aria-label` descriptivo en los 18.
- Clases CSS con **sufijo numérico único** por diagrama (`.t1`…`.n18`), para evitar el bug sistémico de colisión de estilos detectado en T5.
- Paleta del Ayuntamiento: `#0055a0` primario, `#d13c3c` alerta, `#2d8659` ventaja, `#e89822` callout.
- Reparto por sección: §1 → D1-D3 · §2 → D4-D9 · §3 → D10-D13 · §4 → D14-D16 · §5 → D17-D18, con D18 sirviendo también a §6.
- Todos con la línea `[Fuente: …]` a **8 px o más** del borde inferior del `viewBox` y a **12 px o más** del último elemento dibujado (reglas derivadas del QA de T28 y T31).

## 7. Referencias cruzadas a otros temas

Todas validadas contra el temario oficial (BOAM 10.032):

| Tema | Enunciado oficial | Uso en este tema |
|---|---|---|
| **T22** | Arquitectura cliente/servidor y multicapas. Servicios web | Arquitecturas REST y SOAP sobre HTTP |
| **T23** | Aplicaciones web. HTML, XML. Navegadores y lenguajes de script | Vulnerabilidades web y catálogo OWASP |
| **T25** | Accesibilidad, usabilidad y seguridad en el desarrollo | Accesibilidad de la sede y seguridad en el desarrollo |
| **T29** | Control remoto de puesto y gestión de incidencias | Control remoto del puesto frente a acceso remoto por SSH |
| **T30** | Administración de redes de área local | DNS y DHCP internos, monitorización y control de tráfico |
| **T32** | Seguridad de los sistemas. Criptografía y firma digital | Fundamento criptográfico de TLS y de la PKI |
| **T33** | Comunicaciones. Medios de transmisión. Conmutación | Conmutación de paquetes frente a conmutación de circuitos |
| **T34** | El modelo TCP/IP y el modelo OSI. Protocolos TCP/IP | Detalle interno de IP, TCP, UDP, ICMP y ARP |
| **T36** | Seguridad y protección en redes. Perimetral. VPN | Cortafuegos, IDS/IPS y acceso remoto seguro desde el exterior |
| **T37** | Redes locales. Tipología. Dispositivos de interconexión | Conmutadores, encaminadores y métodos de acceso al medio |
| **T39** | Principios básicos del ENS y del ENI | Marco completo del ENS y del ENI |
| **T40** | Herramientas de trabajo en grupo. Videoconferencia | Comunicación corporativa más allá del correo |

## 8. Puntos abiertos para validación del IAM

1. **Frontera con el Tema 34, que es la decisión estructural de este tema.** Se ha aplicado el criterio de que **el T34 explica los protocolos** (campos de cabecera, control de congestión, ARP, ICMP) y **el T35 explica cómo esos protocolos construyen Internet** (sistemas autónomos, BGP, puntos neutros, agotamiento de IPv4, DNS). Por eso §2.1 presenta la pila como marco de referencia sin desmenuzar cada protocolo, mientras que §2.2 desarrolla a fondo el encaminamiento interdominio y el DNS, que el T34 apenas roza. **Procede que el IAM confirme el reparto**, y hacerlo de forma coherente con lo que se escriba en el T34 cuando se genere.

2. **Frontera con el Tema 36.** La seguridad perimetral, los cortafuegos, los IDS/IPS y las VPN se han remitido íntegramente al T36. Aquí solo aparecen TLS, HTTPS, SSH y las medidas del ENS que el enunciado del T35 reclama. Conviene confirmar que el T36 no repetirá TLS.

3. **Frontera con el Tema 32 en materia de criptografía y PKI.** El epígrafe 5.1.2 del esqueleto se titula «Criptografía, certificados digitales e infraestructura PKI», materia que el **T32** desarrolla por extenso. Se ha desarrollado aquí **solo lo que TLS necesita** —cifrado híbrido, certificado X.509, cadena de confianza y revocación— remitiendo el resto. **¿Es la profundidad adecuada, o el IAM prefiere un desarrollo completo de la PKI también aquí?**

4. **Peso relativo de la sección 6.** El esqueleto de partida incluye un sexto bloque de seguridad y normativa que **no figura en el enunciado oficial** del BOAM. Se ha desarrollado como cierre aplicado, sin invadir el T39. Procede confirmar si debe mantenerse con esa extensión.

5. **⚠️ Hallazgo de verificación: el RFC 8446 ya no es la referencia vigente de TLS 1.3.** El contraste contra el índice del RFC Editor reveló que **el RFC 8446 fue obsoletado por el RFC 9846 en julio de 2026**, un mes antes de la generación de este tema, y que el mismo RFC 9846 obsoleta también el **RFC 5246** (TLS 1.2). Se ha optado por **explicar ambos** —citar el RFC 9846 como vigente y conservar la mención del RFC 8446, que es lo que recogen los temarios y la bibliografía— y por advertir expresamente de que **el RFC 9846 no prohíbe TLS 1.2**. **Es un punto a vigilar**: si el tribunal maneja documentación anterior, puede dar por buena una respuesta basada en el RFC 8446. Lo mismo ocurre, en menor medida, con **DHCPv6 (RFC 9915, enero de 2026)** y con **DMARC (RFC 9989 a 9991, mayo de 2026)**.

6. **Datos volátiles que deben reverificarse antes de cada convocatoria.** Este tema es, junto con el T24 y el T31, **el más sensible a la obsolescencia** de toda la serie. Lista de comprobación:
   - Adopción de **IPv6** (superó el 50 % el 28-3-2026) y cifra de **España** (≈ 10 %).
   - **Calendario de duración de los certificados** del CA/Browser Forum (200 días desde el 15-3-2026; 100 días en 2027; 47 días en 2029).
   - Adopción de **HTTP/3** y estado de la migración **post-cuántica** en TLS: publicación como RFC del intercambio híbrido **X25519MLKEM768**, aún pendiente en agosto de 2026.
   - Cifras de **usuarios de Internet** (UIT), **dominios `.es`** (Red.es), **instancias de servidores raíz** y **TLD firmados con DNSSEC**.
   - Estado del **art. 45 de eIDAS 2** y del reconocimiento de los **QWAC** por los navegadores.
   - Transposición de **NIS2** en España.

7. **Denominaciones en castellano.** Se ha optado por traducir de forma sistemática los términos ingleses de uso corriente con la forma española en primer lugar y el original en cursiva: «bloqueo de cabecera de línea» (*head-of-line blocking*), «confidencialidad directa» (*forward secrecy*), «secuencias de órdenes en sitios cruzados» (*cross-site scripting*), «difusión» (*broadcast*), «grapado» (*stapling*), «huella» (*fingerprint*). Se ha seguido, cuando existe, la denominación literal del ENS —que es la que emplea un tribunal—. **Procede que María y Ana validen el criterio**, porque afecta a toda la serie.

8. **Nivel de detalle de los códigos de estado y de los puertos.** Se han incluido las cinco familias de códigos con unos veinte códigos concretos y una tabla de dieciséis servicios con sus puertos. Es el material más rentable del tema para un examen tipo test, pero también el más memorístico. **¿Procede ampliarlo aún más, o el nivel C1 no lo requiere?**
