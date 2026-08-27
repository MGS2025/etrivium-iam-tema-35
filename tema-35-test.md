# Tema 35 — Test de Autoevaluación

> **Título**: Internet: arquitectura de red. Origen, evolución y estado actual. Principales servicios. Protocolos HTTP, HTTPS y SSL/TLS.
> **Formato**: 60 preguntas tipo test A/B/C (formato oficial oposición)
> **Nivel**: C1 — Técnico Auxiliar TIC, Ayuntamiento de Madrid
> **Versión**: v1.0 — Pendiente validación
> **Fecha**: 2026-08-27
> **Fuentes**: ver tema-35-fuentes.md

---

## Instrucciones

- Cada pregunta tiene **3 opciones** (A, B, C). Solo una es correcta.
- Penalización en examen real: respuesta incorrecta descuenta **1/3** del valor de una correcta.
- Tiempo orientativo: 1 minuto por pregunta.
- Distribución: Origen, evolución, gobernanza y RFC (P1-P11), Arquitectura, direccionamiento y DNS (P12-P26), Principales servicios: correo, ficheros, SSH y DHCP (P27-P37), Protocolo HTTP (P38-P48), SSL/TLS y HTTPS (P49-P58), Seguridad y normativa en la Administración (P59-P60).

---

### Pregunta 1

**¿Qué fecha se cita convencionalmente como el nacimiento de Internet tal como se entiende hoy?**

A) El 29 de octubre de 1969, cuando ARPANET conectó sus primeros nodos
B) El 1 de enero de 1983, cuando ARPANET abandonó NCP y adoptó TCP/IP
C) El 6 de agosto de 1991, cuando Berners-Lee publicó el proyecto de la World Wide Web

<details><summary>Respuesta</summary>

**Correcta: B) El 1 de enero de 1983, cuando ARPANET abandonó NCP y adoptó TCP/IP** Ese cambio obligatorio en una única fecha (*flag day*) es lo que crea una familia de protocolos común capaz de unir redes heterogéneas. 1969 es el nacimiento de **ARPANET**, que funcionaba con NCP, y 1991 es la publicación de la **Web**, un servicio posterior.

*Referencia: §1.1.1 [RFC801]*
</details>

---

### Pregunta 2

**Señale la afirmación correcta sobre la relación entre Internet y la World Wide Web.**

A) La Web es uno de los servicios que se ejecutan sobre Internet, junto al correo, el DNS o el acceso remoto
B) Internet y la Web son denominaciones equivalentes del mismo sistema
C) Internet es el conjunto de páginas enlazadas y la Web es la infraestructura de comunicación

<details><summary>Respuesta</summary>

**Correcta: A) La Web es uno de los servicios que se ejecutan sobre Internet, junto al correo, el DNS o el acceso remoto** Internet es la **infraestructura** (la red de redes con TCP/IP) y la Web es **un servicio** que apareció casi veinte años después. La opción C invierte exactamente los términos.

*Referencia: §1.1.1 [FNC]*
</details>

---

### Pregunta 3

**¿Cuál fue el objetivo declarado del proyecto ARPANET?**

A) Garantizar las comunicaciones militares ante un ataque nuclear
B) Ofrecer un servicio comercial de intercambio de mensajes entre universidades
C) Compartir recursos de computación escasos y caros entre centros de investigación

<details><summary>Respuesta</summary>

**Correcta: C) Compartir recursos de computación escasos y caros entre centros de investigación** La resistencia a fallos era una propiedad deseable de la conmutación de paquetes, no la finalidad del proyecto; los propios protagonistas han desmentido por escrito el mito nuclear. El uso comercial no llegó hasta la privatización de NSFNET, en 1995.

*Referencia: §1.1.1 [LEINER]*
</details>

---

### Pregunta 4

**En 1978 se produjo una decisión de diseño determinante para la arquitectura actual. ¿Cuál?**

A) La sustitución de los IMP por encaminadores comerciales
B) La creación del sistema de nombres de dominio
C) La separación del protocolo TCP en dos: IP para el direccionamiento y TCP para la fiabilidad

<details><summary>Respuesta</summary>

**Correcta: C) La separación del protocolo TCP en dos: IP para el direccionamiento y TCP para la fiabilidad** Esa división permitió que sobre IP pudieran construirse transportes distintos, y es la razón de que exista **UDP**. El DNS llegó en 1983-1987.

*Referencia: §1.1.1 [CERF-KAHN]*
</details>

---

### Pregunta 5

**¿Qué tres invenciones combinó la propuesta original de la World Wide Web?**

A) HTML, URI/URL y HTTP
B) HTML, TCP/IP y DNS
C) XML, FTP y SMTP

<details><summary>Respuesta</summary>

**Correcta: A) HTML, URI/URL y HTTP** Un lenguaje de marcado con enlaces, un identificador global de recursos y un protocolo de transferencia. TCP/IP y el DNS son **anteriores** a la Web y pertenecen a la infraestructura, no a la propuesta de Berners-Lee.

*Referencia: §1.1.2 [W3C]*
</details>

---

### Pregunta 6

**En la clasificación habitual de la evolución de la Web, ¿qué caracteriza a la Web 3.0 en el sentido que le dio el W3C?**

A) La descentralización mediante cadenas de bloques y contratos inteligentes
B) La Web Semántica: datos con significado procesable por máquinas mediante RDF, OWL y SPARQL
C) La generación de contenidos por los propios usuarios en redes sociales y wikis

<details><summary>Respuesta</summary>

**Correcta: B) La Web Semántica: datos con significado procesable por máquinas mediante RDF, OWL y SPARQL** La opción A describe la llamada **Web3**, que es una acepción distinta y posterior; la C describe la **Web 2.0**. Distinguir Web 3.0 de Web3 es una trampa habitual.

*Referencia: §1.1.2 [W3C]*
</details>

---

### Pregunta 7

**¿Qué organismo gestiona la asignación de bloques de direcciones IP y de números de sistema autónomo a los registros regionales?**

A) La función IANA, ejercida desde 2016 por PTI, filial de ICANN
B) El IETF, a través de sus grupos de trabajo
C) La Internet Society (ISOC)

<details><summary>Respuesta</summary>

**Correcta: A) La función IANA, ejercida desde 2016 por PTI, filial de ICANN** La cadena es **IANA → RIR → LIR (operador) → usuario final**. El IETF escribe los estándares y la ISOC es el paraguas institucional; ninguno reparte direcciones.

*Referencia: §1.2.1 [ICANN]*
</details>

---

### Pregunta 8

**¿A qué registro regional de Internet pertenece España?**

A) ARIN
B) APNIC
C) RIPE NCC

<details><summary>Respuesta</summary>

**Correcta: C) RIPE NCC** Cubre Europa, Oriente Medio y Asia Central, con sede en los Países Bajos. ARIN cubre Norteamérica y APNIC la región Asia-Pacífico.

*Referencia: §1.2.1 [RIPE]*
</details>

---

### Pregunta 9

**Señale la afirmación correcta sobre el reparto de competencias entre organismos.**

A) El W3C es el organismo que estandariza el protocolo HTTP
B) El IETF estandariza HTTP y TLS, mientras que el W3C estandariza HTML y CSS
C) El Foro de Gobernanza de Internet (IGF) adopta decisiones vinculantes sobre la raíz del DNS

<details><summary>Respuesta</summary>

**Correcta: B) El IETF estandariza HTTP y TLS, mientras que el W3C estandariza HTML y CSS** Aunque HTTP sea «el protocolo de la Web», es un estándar **del IETF**. Y el IGF es un foro **de diálogo** auspiciado por la ONU, sin capacidad normativa.

*Referencia: §1.2.1 [IETF]*
</details>

---

### Pregunta 10

**Un documento se publica como Internet-Draft del IETF. ¿Qué consecuencia tiene ese estado?**

A) No es un estándar y caduca a los seis meses si no se actualiza, por lo que no puede citarse como referencia normativa
B) Es un estándar provisional de obligado cumplimiento durante seis meses
C) Equivale a un RFC de categoría *Informational* con número asignado

<details><summary>Respuesta</summary>

**Correcta: A) No es un estándar y caduca a los seis meses si no se actualiza, por lo que no puede citarse como referencia normativa** Solo al final del proceso —adopción por el grupo de trabajo, última llamada y aprobación del IESG— se publica como **RFC** con número definitivo.

*Referencia: §1.2.2 [RFC-ED]*
</details>

---

### Pregunta 11

**¿Qué ocurre cuando el IETF necesita corregir el contenido de un RFC ya publicado?**

A) Se publica una nueva revisión con el mismo número y una letra de versión
B) El RFC Editor edita el documento original y anota la fecha del cambio
C) Se publica un RFC nuevo que obsoleta o actualiza al anterior, porque el publicado es inmutable

<details><summary>Respuesta</summary>

**Correcta: C) Se publica un RFC nuevo que obsoleta o actualiza al anterior, porque el publicado es inmutable** Es la regla básica de la serie. Por eso HTTP/1.1, especificado en el RFC 2616, pasó por los RFC 723x y hoy está en los **RFC 9110-9112**.

*Referencia: §1.2.2 [RFC-ED]*
</details>

---

### Pregunta 12

**El modelo TCP/IP y el modelo OSI se corresponden de la siguiente manera:**

A) Ambos tienen siete capas con distinta denominación
B) La capa de aplicación de TCP/IP equivale a las capas de aplicación, presentación y sesión de OSI
C) La capa de acceso a red de TCP/IP equivale únicamente a la capa física de OSI

<details><summary>Respuesta</summary>

**Correcta: B) La capa de aplicación de TCP/IP equivale a las capas de aplicación, presentación y sesión de OSI** TCP/IP tiene **cuatro** capas frente a las **siete** de OSI, y su capa de acceso a red absorbe **dos**: enlace de datos y física.

*Referencia: §2.1.1 [RFC1122]*
</details>

---

### Pregunta 13

**¿Cuál es la unidad de datos (PDU) propia de la capa de internet o de red?**

A) El paquete o datagrama IP
B) La trama
C) El segmento

<details><summary>Respuesta</summary>

**Correcta: A) El paquete o datagrama IP** La **trama** es la PDU de la capa de enlace y el **segmento** la de TCP (la de UDP se denomina datagrama). En la capa de aplicación se habla de mensaje.

*Referencia: §2.1.1 [RFC1122]*
</details>

---

### Pregunta 14

**Durante el encaminamiento de un paquete a través de varios encaminadores:**

A) Cambian las direcciones IP de origen y destino, y se conservan las direcciones MAC
B) Se conservan tanto las direcciones IP como las MAC hasta el destino final
C) Cambian las direcciones MAC en cada salto y se conservan las direcciones IP de extremo a extremo

<details><summary>Respuesta</summary>

**Correcta: C) Cambian las direcciones MAC en cada salto y se conservan las direcciones IP de extremo a extremo** Las direcciones MAC son locales a cada enlace. La única excepción a la conservación de las IP es la presencia de un **NAT**, cuya función es precisamente reescribirlas.

*Referencia: §2.1.2 [RFC1122]*
</details>

---

### Pregunta 15

**Respecto de la fragmentación de paquetes, IPv6 se diferencia de IPv4 en que:**

A) Elimina por completo la posibilidad de fragmentar
B) Solo el nodo origen puede fragmentar; los encaminadores intermedios no lo hacen
C) Fragmenta siempre en el encaminador de salida de la red local

<details><summary>Respuesta</summary>

**Correcta: B) Solo el nodo origen puede fragmentar; los encaminadores intermedios no lo hacen** El origen descubre la MTU del camino con *Path MTU Discovery*, y si un paquete no cabe se genera un mensaje ICMPv6 de «paquete demasiado grande». La fragmentación no desaparece: cambia de responsable.

*Referencia: §2.1.2 [RFC8200]*
</details>

---

### Pregunta 16

**¿Qué es un sistema autónomo (AS)?**

A) Un conjunto de redes bajo una misma administración que presenta hacia el exterior una política de encaminamiento única
B) Un encaminador capaz de funcionar sin configuración manual
C) Una red local aislada de Internet por un cortafuegos

<details><summary>Respuesta</summary>

**Correcta: A) Un conjunto de redes bajo una misma administración que presenta hacia el exterior una política de encaminamiento única** Se identifica con un **ASN** de 32 bits asignado por la IANA a través de los RIR, y se relaciona con los demás mediante **BGP**.

*Referencia: §2.2.1 [RFC4271]*
</details>

---

### Pregunta 17

**Señale la afirmación correcta sobre BGP.**

A) Es un protocolo de encaminamiento interior que optimiza el número de saltos
B) Es el único protocolo de encaminamiento exterior de Internet, funciona sobre TCP/179 y decide por política
C) Es un protocolo de estado de enlace que sustituye a OSPF dentro del sistema autónomo

<details><summary>Respuesta</summary>

**Correcta: B) Es el único protocolo de encaminamiento exterior de Internet, funciona sobre TCP/179 y decide por política** BGP-4 es un protocolo de **vector de caminos**. RIP, OSPF, IS-IS y EIGRP son protocolos **interiores** (IGP) y sí optimizan métricas técnicas.

*Referencia: §2.2.1 [RFC4271]*
</details>

---

### Pregunta 18

**¿Qué diferencia el tránsito del *peering* entre operadores?**

A) El tránsito es gratuito y el *peering* se factura por volumen intercambiado
B) Ambos dan acceso a la totalidad de Internet, y solo se diferencian en la tecnología del enlace
C) El tránsito se paga y da acceso a todo Internet; el *peering* suele ser gratuito y solo alcanza al otro AS y a sus clientes

<details><summary>Respuesta</summary>

**Correcta: C) El tránsito se paga y da acceso a todo Internet; el *peering* suele ser gratuito y solo alcanza al otro AS y a sus clientes** Los puntos neutros (**IXP**), como ESPANIX o DE-CIX Madrid, son la infraestructura donde el *peering* se realiza de forma masiva, con el efecto de reducir costes y latencia.

*Referencia: §2.2.1 [ESPANIX]*
</details>

---

### Pregunta 19

**¿Qué son las direcciones del rango 100.64.0.0/10 definido en el RFC 6598?**

A) El espacio compartido reservado para el NAT a gran escala del operador (CGNAT)
B) Un tercer rango de direcciones privadas de uso interno, equivalente a las del RFC 1918
C) El rango asignado a los servidores raíz del DNS

<details><summary>Respuesta</summary>

**Correcta: A) El espacio compartido reservado para el NAT a gran escala del operador (CGNAT)** Su consecuencia práctica más relevante es que **varios abonados comparten una misma IP pública**, de modo que para identificar a un usuario ya no basta con la dirección y la hora: hace falta también el **puerto de origen**.

*Referencia: §2.2.2 [RFC6598]*
</details>

---

### Pregunta 20

**Señale la afirmación correcta sobre IPv6.**

A) Utiliza direcciones de 64 bits y mantiene la difusión (*broadcast*) de IPv4
B) Utiliza direcciones de 128 bits, tiene cabecera fija de 40 bytes y sustituye la difusión por multidifusión y anycast
C) Utiliza direcciones de 128 bits y conserva la suma de control de la cabecera para mayor fiabilidad

<details><summary>Respuesta</summary>

**Correcta: B) Utiliza direcciones de 128 bits, tiene cabecera fija de 40 bytes y sustituye la difusión por multidifusión y anycast** Además **elimina la suma de control** de la cabecera —se delega en las capas superior e inferior— y sustituye ARP por el protocolo de descubrimiento de vecinos (**NDP**).

*Referencia: §2.2.2 [RFC8200]*
</details>

---

### Pregunta 21

**Una organización necesita que sus equipos, que solo hablan IPv6, accedan a servicios que solo están publicados en IPv4. ¿Qué mecanismo procede?**

A) Ninguno: basta con activar IPv6 en el encaminador, porque ambos protocolos son compatibles
B) Un túnel 6in4 entre los dos extremos
C) Una traducción con NAT64 y DNS64

<details><summary>Respuesta</summary>

**Correcta: C) Una traducción con NAT64 y DNS64** Los túneles sirven para transportar **IPv6 a través de** una zona IPv4, no para que un nodo solo-IPv6 hable con uno solo-IPv4. Y la opción A es falsa: los dos protocolos son **incompatibles**, y siempre hace falta doble pila, túnel o traducción.

*Referencia: §2.2.2 [RFC6146]*
</details>

---

### Pregunta 22

**En la resolución de un nombre de dominio, ¿qué tipo de consulta lanza el cliente a su resolutor?**

A) Una consulta recursiva: el resolutor asume el trabajo de obtener la respuesta final
B) Una consulta iterativa, que el cliente repite contra la raíz, el TLD y el servidor autoritativo
C) Una transferencia de zona, que le entrega los registros del dominio

<details><summary>Respuesta</summary>

**Correcta: A) Una consulta recursiva: el resolutor asume el trabajo de obtener la respuesta final** Las **iterativas** son las que hace el propio resolutor contra los servidores autoritativos. La transferencia de zona (AXFR) es una operación entre servidores, que además debe estar restringida.

*Referencia: §2.2.3 [RFC1034]*
</details>

---

### Pregunta 23

**¿Por qué existen exactamente trece identidades de servidor raíz del DNS?**

A) Porque son las trece organizaciones autorizadas por la ONU para operar la raíz
B) Por una limitación histórica: la lista completa debía caber en un único datagrama UDP de 512 bytes
C) Porque el protocolo DNS reserva cuatro bits para identificarlos

<details><summary>Respuesta</summary>

**Correcta: B) Por una limitación histórica: la lista completa debía caber en un único datagrama UDP de 512 bytes** La restricción se superó con **EDNS0**, pero el número se mantiene por compatibilidad. Lo que sí crece es el número de **instancias físicas**: más de 2.000 en 2026, gracias a **anycast**.

*Referencia: §2.2.3 [ICANN]*
</details>

---

### Pregunta 24

**¿Qué registro DNS indica qué autoridades de certificación pueden emitir certificados para un dominio?**

A) El registro TXT
B) El registro SRV
C) El registro CAA

<details><summary>Respuesta</summary>

**Correcta: C) El registro CAA** Es una medida barata y muy eficaz para una organización pública: impide que una AC distinta de la contratada emita un certificado válido para el dominio municipal. El registro TXT da soporte a SPF, DKIM y DMARC, y el SRV publica servicio, protocolo y puerto.

*Referencia: §2.2.3 [RFC8659]*
</details>

---

### Pregunta 25

**Señale la afirmación correcta sobre DNSSEC.**

A) Firma digitalmente las respuestas y aporta autenticidad e integridad, pero no confidencialidad
B) Cifra las consultas DNS entre el cliente y el resolutor, impidiendo que un tercero sepa qué sitios se visitan
C) Sustituye a DNS sobre TLS y a DNS sobre HTTPS, que quedan obsoletos donde se implanta

<details><summary>Respuesta</summary>

**Correcta: A) Firma digitalmente las respuestas y aporta autenticidad e integridad, pero no confidencialidad** El cifrado del transporte lo aportan **DoT** (TCP/853) y **DoH** (HTTPS/443), que en cambio **no** garantizan la autenticidad del dato de la zona. Son mecanismos **complementarios**.

*Referencia: §2.2.3 [RFC4033]*
</details>

---

### Pregunta 26

**El DNS emplea el puerto 53. ¿En qué casos utiliza TCP en lugar de UDP?**

A) Nunca: el DNS es un protocolo exclusivamente UDP
B) Solo cuando el cliente lo solicita expresamente en la configuración del sistema
C) Cuando la respuesta excede el tamaño admisible y, siempre, en las transferencias de zona

<details><summary>Respuesta</summary>

**Correcta: C) Cuando la respuesta excede el tamaño admisible y, siempre, en las transferencias de zona** La respuesta truncada se marca con el bit **TC** y el cliente reintenta por TCP. Las transferencias **AXFR** e **IXFR** van siempre por TCP y deben restringirse: una AXFR abierta entrega el mapa completo de la organización.

*Referencia: §2.2.3 [RFC1035]*
</details>

---

### Pregunta 27

**¿Qué protocolo se utiliza para enviar un mensaje de correo electrónico desde el cliente hacia el servidor y entre servidores?**

A) IMAP
B) SMTP
C) POP3

<details><summary>Respuesta</summary>

**Correcta: B) SMTP** Es el protocolo de **envío y tránsito**. POP3 e IMAP son protocolos de **acceso al buzón**: sirven para recoger, no para enviar. Un cliente de correo necesita configurados los dos tipos: uno de salida y uno de entrada.

*Referencia: §3.1.1 [RFC5321]*
</details>

---

### Pregunta 28

**Un empleado municipal consulta el correo desde el ordenador de la oficina y desde el móvil, y necesita ver en ambos el mismo estado de las carpetas. ¿Qué protocolo de acceso procede?**

A) IMAP, porque mantiene los mensajes en el servidor y sincroniza carpetas y estado
B) POP3, porque descarga los mensajes y libera espacio en el servidor
C) SMTP con autenticación, configurado en los dos dispositivos

<details><summary>Respuesta</summary>

**Correcta: A) IMAP, porque mantiene los mensajes en el servidor y sincroniza carpetas y estado** POP3, en su comportamiento por defecto, **descarga y borra**, de modo que cada dispositivo acabaría con una copia distinta. SMTP no sirve para consultar el buzón.

*Referencia: §3.1.1 [RFC9051]*
</details>

---

### Pregunta 29

**¿Qué puerto se emplea para el envío de correo desde el cliente al servidor (*submission*) con STARTTLS?**

A) El 25
B) El 993
C) El 587

<details><summary>Respuesta</summary>

**Correcta: C) El 587** El **25** queda para el tránsito entre servidores y el **465** para el envío con TLS implícito. El **993** es IMAP sobre TLS, que es acceso al buzón, no envío.

*Referencia: §3.1.1 [RFC8314]*
</details>

---

### Pregunta 30

**Señale la afirmación correcta sobre SPF, DKIM y DMARC.**

A) Los tres cifran el contenido del mensaje de extremo a extremo
B) SPF autoriza servidores emisores, DKIM firma criptográficamente el mensaje y DMARC exige el alineamiento y fija la política ante el fallo
C) DKIM sustituye a SPF, que quedó obsoleto tras la publicación del RFC 9989

<details><summary>Respuesta</summary>

**Correcta: B) SPF autoriza servidores emisores, DKIM firma criptográficamente el mensaje y DMARC exige el alineamiento y fija la política ante el fallo** Los tres se publican como registros **TXT en el DNS** y ninguno cifra el contenido: para eso están S/MIME o PGP. DMARC fue reeditado en mayo de 2026 por los RFC 9989, 9990 y 9991, sin que ello afecte a la vigencia de SPF.

*Referencia: §3.1.1 [RFC9989]*
</details>

---
### Pregunta 31

**En una transferencia FTP en modo activo:**

A) El servidor abre la conexión de datos hacia el cliente desde su puerto 20, lo que suele bloquear el cortafuegos del cliente
B) El cliente abre las dos conexiones, la de control y la de datos
C) Se emplea una única conexión TCP para control y datos

<details><summary>Respuesta</summary>

**Correcta: A) El servidor abre la conexión de datos hacia el cliente desde su puerto 20, lo que suele bloquear el cortafuegos del cliente** Por eso el modo habitual hoy es el **pasivo** (comando `PASV`), en el que es el cliente quien abre ambas conexiones. FTP usa siempre **dos** canales: control en el 21 y datos.

*Referencia: §3.1.2 [RFC959]*
</details>

---

### Pregunta 32

**Señale la afirmación correcta sobre SFTP y FTPS.**

A) Son dos nombres del mismo protocolo: FTP con cifrado TLS
B) SFTP es un subsistema de SSH que usa el puerto 22, mientras que FTPS es FTP envuelto en TLS
C) SFTP es FTP sobre TLS en el puerto 990 y FTPS es una extensión de SSH

<details><summary>Respuesta</summary>

**Correcta: B) SFTP es un subsistema de SSH que usa el puerto 22, mientras que FTPS es FTP envuelto en TLS** Es la confusión más frecuente del epígrafe: **SFTP no tiene ninguna relación con FTP** pese al nombre, y por eso funciona con un solo canal y sin los problemas de cortafuegos del modo activo.

*Referencia: §3.1.2 [RFC4251]*
</details>

---

### Pregunta 33

**¿Cuál de estas capas NO forma parte de la arquitectura del protocolo SSH?**

A) La capa de transporte, que cifra y autentica al servidor
B) La capa de conexión, que multiplexa canales
C) La capa de presentación, que negocia la codificación de los datos

<details><summary>Respuesta</summary>

**Correcta: C) La capa de presentación, que negocia la codificación de los datos** SSH se estructura en **tres** capas: transporte, autenticación de usuario y conexión. La «capa de presentación» pertenece al modelo OSI, no a SSH.

*Referencia: §3.2.1 [RFC4251]*
</details>

---

### Pregunta 34

**Al conectarse por primera vez a un servidor SSH, el cliente muestra la huella de la clave del servidor y pide confirmación. ¿Qué modelo de confianza aplica y qué implica un cambio posterior de esa huella?**

A) Confianza en el primer uso: si la huella cambia después, el cliente aborta la conexión porque puede haber un ataque de intermediario
B) Confianza en una autoridad de certificación: si la huella cambia, basta con aceptar el nuevo certificado
C) Confianza delegada en el servidor DNS: el cambio de huella indica que se ha actualizado el registro A

<details><summary>Respuesta</summary>

**Correcta: A) Confianza en el primer uso: si la huella cambia después, el cliente aborta la conexión porque puede haber un ataque de intermediario** La huella se guarda en `known_hosts`. El aviso puede deberse a una reinstalación legítima del servidor, pero **nunca debe ignorarse sin comprobarlo**.

*Referencia: §3.2.1 [RFC4251]*
</details>

---

### Pregunta 35

**El intercambio DHCP se resume en el acrónimo DORA. ¿Cuál es su secuencia correcta?**

A) Discover, Offer, Renew, Acknowledge
B) Discover, Offer, Request, Acknowledge
C) Demand, Offer, Request, Assign

<details><summary>Respuesta</summary>

**Correcta: B) Discover, Offer, Request, Acknowledge** El cliente descubre en difusión, uno o varios servidores ofrecen, el cliente solicita formalmente una oferta —también en difusión, para que los demás retiren la suya— y el servidor confirma la concesión. La renovación posterior se intenta al **50 %** de la concesión.

*Referencia: §3.2.2 [RFC2131]*
</details>

---

### Pregunta 36

**¿Qué puertos utiliza DHCP en IPv4?**

A) TCP 67 en el cliente y TCP 68 en el servidor
B) UDP 546 en el servidor y UDP 547 en el cliente
C) UDP 67 en el servidor y UDP 68 en el cliente

<details><summary>Respuesta</summary>

**Correcta: C) UDP 67 en el servidor y UDP 68 en el cliente** Los puertos **546 y 547** corresponden a **DHCPv6** (547 servidor y 546 cliente), reeditado en enero de 2026 por el RFC 9915, que es además **STD 102**.

*Referencia: §3.2.2 [RFC2131]*
</details>

---

### Pregunta 37

**En una red IPv6 en la que se exige poder determinar qué equipo tenía cada dirección en cada momento, ¿qué opción de configuración es la adecuada?**

A) DHCPv6 con estado, porque mantiene un registro central de las concesiones
B) SLAAC, porque cada equipo se construye su dirección a partir del prefijo anunciado
C) Es indiferente: ambas mantienen registro de las direcciones asignadas

<details><summary>Respuesta</summary>

**Correcta: A) DHCPv6 con estado, porque mantiene un registro central de las concesiones** **SLAAC** es *sin estado*: el encaminador anuncia el prefijo y no lleva registro de quién toma qué dirección, lo que dificulta la **trazabilidad** exigida por el ENS. Si se usa SLAAC, hay que complementarlo vigilando la tabla de vecinos.

*Referencia: §3.2.2 [RFC9915]*
</details>

---

### Pregunta 38

**¿Cuál es la especificación vigente del protocolo HTTP?**

A) El RFC 2616, de 1999
B) La serie RFC 7230 a 7235, de 2014
C) La serie RFC 9110 a 9114, de junio de 2022

<details><summary>Respuesta</summary>

**Correcta: C) La serie RFC 9110 a 9114, de junio de 2022** El RFC 2616 fue sustituido por la serie 723x y esta por la actual, que además **separa la semántica de la sintaxis** de cada versión: RFC 9110 (semántica, STD 97), 9111 (caché), 9112 (HTTP/1.1), 9113 (HTTP/2) y 9114 (HTTP/3).

*Referencia: §4.1.1 [RFC9110]*
</details>

---

### Pregunta 39

**Que HTTP sea un protocolo «sin estado» significa que:**

A) Cierra la conexión TCP después de cada recurso transferido
B) El servidor no recuerda por sí mismo nada de las peticiones anteriores: cada una se interpreta de forma independiente
C) No admite autenticación de usuarios

<details><summary>Respuesta</summary>

**Correcta: B) El servidor no recuerda por sí mismo nada de las peticiones anteriores: cada una se interpreta de forma independiente** No hay que confundirlo con «sin conexión»: desde **HTTP/1.1** las conexiones son **persistentes** por defecto, y aun así el protocolo sigue siendo sin estado. El estado de la aplicación se construye con cookies, sesiones o tokens.

*Referencia: §4.1.1 [RFC9110]*
</details>

---

### Pregunta 40

**¿Qué aportó HTTP/1.1 respecto de HTTP/1.0?**

A) Conexiones persistentes por defecto y la cabecera Host obligatoria, que hace posible el alojamiento virtual
B) La codificación binaria de los mensajes y la multiplexación de corrientes
C) El transporte sobre QUIC y el cifrado obligatorio

<details><summary>Respuesta</summary>

**Correcta: A) Conexiones persistentes por defecto y la cabecera Host obligatoria, que hace posible el alojamiento virtual** La codificación binaria y la multiplexación llegaron con **HTTP/2**, y el transporte sobre QUIC con **HTTP/3**.

*Referencia: §4.1.2 [RFC9112]*
</details>

---

### Pregunta 41

**HTTP/2 introdujo la multiplexación de corrientes sobre una única conexión. ¿Qué problema NO llegó a resolver?**

A) La compresión de las cabeceras repetidas
B) El bloqueo de cabecera de línea en el transporte: la pérdida de un segmento TCP detiene todas las corrientes
C) La necesidad de abrir varias conexiones por dominio para descargar recursos en paralelo

<details><summary>Respuesta</summary>

**Correcta: B) El bloqueo de cabecera de línea en el transporte: la pérdida de un segmento TCP detiene todas las corrientes** HTTP/2 sí resolvió el bloqueo **en la capa de aplicación** y sí comprimió cabeceras con **HPACK**. El bloqueo del transporte solo desaparece con **HTTP/3**, porque QUIC gestiona cada corriente de forma independiente.

*Referencia: §4.1.2 [RFC9113]*
</details>

---

### Pregunta 42

**HTTP/3 se apoya en QUIC. Señale la afirmación correcta.**

A) QUIC es una variante de TCP optimizada para la web, definida en el RFC 9114
B) HTTP/3 puede funcionar en claro sobre UDP si el servidor así lo configura
C) QUIC se ejecuta sobre UDP, integra TLS 1.3 en su propio establecimiento y por eso HTTP/3 va siempre cifrado

<details><summary>Respuesta</summary>

**Correcta: C) QUIC se ejecuta sobre UDP, integra TLS 1.3 en su propio establecimiento y por eso HTTP/3 va siempre cifrado** QUIC está definido en el **RFC 9000** (el 9114 es HTTP/3) y reimplementa en espacio de usuario la fiabilidad que TCP ofrece en el núcleo. **No existe un HTTP/3 en claro**.

*Referencia: §4.1.2 [RFC9000]*
</details>

---

### Pregunta 43

**¿Qué ventaja aporta QUIC a un usuario que pasa de la red Wi-Fi a la red móvil en mitad de una descarga?**

A) La migración de conexión: como esta se identifica por un identificador propio y no por la cuádrupla IP y puerto, la sesión se conserva
B) La retransmisión selectiva, que recupera los paquetes perdidos durante el cambio de red
C) Ninguna: el cambio de red obliga siempre a reiniciar la conexión

<details><summary>Respuesta</summary>

**Correcta: A) La migración de conexión: como esta se identifica por un identificador propio y no por la cuádrupla IP y puerto, la sesión se conserva** Es una de las dos ventajas más citadas de QUIC, junto con el **0-RTT** en la reanudación, que solo debe emplearse con peticiones idempotentes por el riesgo de repetición.

*Referencia: §4.1.2 [RFC9000]*
</details>

---

### Pregunta 44

**Señale la afirmación correcta sobre los métodos HTTP.**

A) POST es idempotente porque siempre produce el mismo recurso
B) GET, HEAD, OPTIONS y TRACE son seguros e idempotentes; PUT y DELETE son idempotentes pero no seguros
C) DELETE no es idempotente, porque al repetirlo el servidor devuelve un código de error distinto

<details><summary>Respuesta</summary>

**Correcta: B) GET, HEAD, OPTIONS y TRACE son seguros e idempotentes; PUT y DELETE son idempotentes pero no seguros** **Seguro** significa que no pretende modificar el estado del servidor; **idempotente**, que repetir la petición produce el mismo efecto. La opción C confunde el **código de respuesta** con el **efecto**, que es lo que define la idempotencia. `POST` y `PATCH` no son ni seguros ni idempotentes.

*Referencia: §4.2.1 [RFC9110]*
</details>

---

### Pregunta 45

**Una aplicación devuelve 401 en lugar de 403. ¿Qué está indicando?**

A) Que el recurso solicitado no existe en el servidor
B) Que el usuario está autenticado pero carece de permisos sobre el recurso
C) Que el usuario no está autenticado o sus credenciales no son válidas

<details><summary>Respuesta</summary>

**Correcta: C) Que el usuario no está autenticado o sus credenciales no son válidas** El **403 Forbidden** es el caso contrario: identidad acreditada pero **sin autorización**, de modo que volver a identificarse no serviría de nada. El «no existe» es el **404**.

*Referencia: §4.2.1 [RFC9110]*
</details>

---

### Pregunta 46

**Un formulario de la sede electrónica envía datos personales. ¿Qué afirmación es correcta?**

A) Con POST los datos viajan en el cuerpo y no quedan escritos en la URL, pero solo HTTPS garantiza su confidencialidad
B) POST cifra el contenido del formulario, por lo que no es necesario HTTPS
C) Con GET los datos viajan cifrados en la cadena de consulta

<details><summary>Respuesta</summary>

**Correcta: A) Con POST los datos viajan en el cuerpo y no quedan escritos en la URL, pero solo HTTPS garantiza su confidencialidad** **POST no cifra nada**. La cadena de consulta de un `GET` queda registrada en los *logs* del servidor y de los intermediarios, y en el historial del navegador: por eso nunca deben ponerse datos sensibles en la URL.

*Referencia: §4.2.1 [RFC9110]*
</details>

---

### Pregunta 47

**¿Qué atributo de una cookie impide que sea accesible desde JavaScript y, con ello, mitiga su robo mediante secuencias de órdenes en sitios cruzados?**

A) Secure
B) SameSite
C) HttpOnly

<details><summary>Respuesta</summary>

**Correcta: C) HttpOnly** **Secure** limita el envío a conexiones HTTPS —protege frente a la interceptación en red— y **SameSite** controla el envío en peticiones de origen cruzado, mitigando la falsificación de petición (**CSRF**). Los tres protegen frente a amenazas distintas y deben combinarse.

*Referencia: §4.2.2 [RFC6265]*
</details>

---

### Pregunta 48

**Una página de la sede muestra datos personales del ciudadano y se accede desde un puesto compartido. ¿Qué directiva de caché procede?**

A) Cache-Control: no-cache, porque prohíbe almacenar la respuesta
B) Cache-Control: no-store, junto con private, porque prohíbe almacenar la respuesta en cualquier caché
C) Cache-Control: max-age=0, porque equivale a no guardar nada

<details><summary>Respuesta</summary>

**Correcta: B) Cache-Control: no-store, junto con private, porque prohíbe almacenar la respuesta en cualquier caché** La trampa está en `no-cache`, que **sí permite almacenar** la respuesta y solo obliga a **revalidarla** antes de reutilizarla. Es una distinción que se pregunta con frecuencia.

*Referencia: §4.2.2 [RFC9111]*
</details>

---

### Pregunta 49

**¿Cuál es la situación de SSL y de las distintas versiones de TLS en 2026?**

A) SSL 2.0 y 3.0 están prohibidos, TLS 1.0 y 1.1 se declararon obsoletos por el RFC 8996, y siguen vigentes TLS 1.2 y TLS 1.3
B) SSL 3.0 sigue admitiéndose por compatibilidad con navegadores antiguos
C) Solo TLS 1.3 está admitido; TLS 1.2 quedó prohibido al publicarse el RFC 9846

<details><summary>Respuesta</summary>

**Correcta: A) SSL 2.0 y 3.0 están prohibidos, TLS 1.0 y 1.1 se declararon obsoletos por el RFC 8996, y siguen vigentes TLS 1.2 y TLS 1.3** El **RFC 9846** (julio de 2026) reedita TLS 1.3 y obsoleta las especificaciones anteriores, incluida la del RFC 5246, pero **no prohíbe TLS 1.2**: unifica la especificación y añade requisitos para sus implementaciones.

*Referencia: §5.1.1 [RFC9846]*
</details>

---

### Pregunta 50

**¿Cuál es el subprotocolo de TLS que encapsula a todos los demás?**

A) El protocolo Handshake, porque es el primero en ejecutarse
B) El protocolo Alert, porque puede interrumpir la sesión en cualquier momento
C) El protocolo Record, porque fragmenta, cifra y protege la integridad de todo lo que transportan los demás

<details><summary>Respuesta</summary>

**Correcta: C) El protocolo Record, porque fragmenta, cifra y protege la integridad de todo lo que transportan los demás** El **Handshake** es el que negocia los algoritmos, autentica mediante certificado y acuerda las claves, pero viaja **dentro** del Record, igual que Alert, Change Cipher Spec y los datos de aplicación.

*Referencia: §5.1.1 [RFC9846]*
</details>

---

### Pregunta 51

**Señale la afirmación correcta sobre TLS 1.3.**

A) Mantiene el intercambio de claves RSA estático por motivos de compatibilidad
B) Exige confidencialidad directa, admite solo cifrado autenticado AEAD y completa el saludo en una vuelta (1-RTT)
C) Elimina por completo el uso de RSA, que ya no puede emplearse ni para firmar

<details><summary>Respuesta</summary>

**Correcta: B) Exige confidencialidad directa, admite solo cifrado autenticado AEAD y completa el saludo en una vuelta (1-RTT)** La trampa está en la opción C: TLS 1.3 elimina RSA **como método de intercambio de claves**, pero RSA **sigue admitido para la firma** del certificado. También suprime la renegociación y la compresión.

*Referencia: §5.1.1 [RFC9846]*
</details>

---

### Pregunta 52

**¿Qué consecuencia tiene que TLS 1.3 imponga la confidencialidad directa (*forward secrecy*)?**

A) Que comprometer en el futuro la clave privada del servidor no permite descifrar el tráfico capturado en el pasado
B) Que el servidor puede descifrar en cualquier momento las sesiones antiguas para auditarlas
C) Que ya no es necesario el certificado del servidor, porque las claves se generan en el cliente

<details><summary>Respuesta</summary>

**Correcta: A) Que comprometer en el futuro la clave privada del servidor no permite descifrar el tráfico capturado en el pasado** Se consigue porque el acuerdo de claves es **Diffie-Hellman efímero** (ECDHE o DHE) y el material de sesión no se deriva de la clave del certificado. El certificado sigue siendo imprescindible para **autenticar** al servidor.

*Referencia: §5.1.1 [RFC9846]*
</details>

---

### Pregunta 53

**Al validar el certificado de un servidor, ¿qué extensión determina hoy si el nombre solicitado corresponde a ese certificado?**

A) El campo CN del sujeto
B) La extensión keyUsage
C) La extensión subjectAltName (SAN)

<details><summary>Respuesta</summary>

**Correcta: C) La extensión subjectAltName (SAN)** Es la única que miran los navegadores modernos, y la que permite incluir **varios nombres** en un mismo certificado. La validación comprueba además la firma de la AC, la vigencia, las restricciones básicas y la revocación.

*Referencia: §5.1.2 [RFC5280]*
</details>

---

### Pregunta 54

**Respecto de la duración de los certificados TLS públicos, según el calendario aprobado por el CA/Browser Forum:**

A) El máximo se mantiene en 398 días hasta 2030
B) El máximo es de 200 días desde el 15 de marzo de 2026, de 100 días desde 2027 y de 47 días desde 2029
C) La duración la fija libremente cada autoridad de certificación

<details><summary>Respuesta</summary>

**Correcta: B) El máximo es de 200 días desde el 15 de marzo de 2026, de 100 días desde 2027 y de 47 días desde 2029** Es el acuerdo **SC-081v3**, aprobado en abril de 2025. Su consecuencia organizativa es que la renovación manual deja de ser viable y hay que implantar **renovación automatizada** e inventario de certificados.

*Referencia: §5.1.2 [CABF]*
</details>

---

### Pregunta 55

**Señale la afirmación correcta sobre los mecanismos de revocación de certificados.**

A) La CRL es una lista firmada de certificados revocados que puede estar desactualizada, mientras que OCSP consulta el estado en línea de un certificado concreto
B) OCSP sustituyó a las CRL, que ya no se emplean desde 2020
C) El grapado OCSP obliga al navegador a consultar directamente a la autoridad de certificación en cada conexión

<details><summary>Respuesta</summary>

**Correcta: A) La CRL es una lista firmada de certificados revocados que puede estar desactualizada, mientras que OCSP consulta el estado en línea de un certificado concreto** El **grapado** hace justo lo contrario de lo que dice la opción C: es **el servidor** quien adjunta una respuesta OCSP reciente, evitando la consulta del navegador y el problema de privacidad que llevó a Let's Encrypt a apagar su servicio OCSP en agosto de 2025.

*Referencia: §5.1.2 [RFC6960]*
</details>

---

### Pregunta 56

**¿Qué es exactamente HTTPS?**

A) Un protocolo distinto de HTTP, con métodos y códigos de estado propios
B) HTTP transportado dentro de una sesión TLS, normalmente en el puerto 443, con la misma semántica que HTTP
C) Una extensión de TLS que sustituye a HTTP en las sedes electrónicas

<details><summary>Respuesta</summary>

**Correcta: B) HTTP transportado dentro de una sesión TLS, normalmente en el puerto 443, con la misma semántica que HTTP** Los métodos, los códigos y las cabeceras son idénticos. El orden de las capas es **TCP → TLS → HTTP**; en HTTP/3, **UDP → QUIC (con TLS 1.3 integrado) → HTTP/3**.

*Referencia: §5.2.1 [RFC9110]*
</details>

---

### Pregunta 57

**Un ciudadano accede por HTTPS a la sede electrónica. ¿Qué información sigue siendo visible para quien observe la red?**

A) El contenido del formulario que envía y las cookies de sesión
B) La ruta y la cadena de consulta de la URL solicitada
C) La dirección IP del servidor y, salvo que se emplee ECH, el nombre del sitio en la extensión SNI del saludo

<details><summary>Respuesta</summary>

**Correcta: C) La dirección IP del servidor y, salvo que se emplee ECH, el nombre del sitio en la extensión SNI del saludo** El cuerpo, las cabeceras, las cookies y la ruta **sí van cifrados**. El SNI viaja en claro porque el servidor todavía no sabe qué certificado debe presentar; **ECH** es la solución en despliegue.

*Referencia: §5.2.1 [RFC8446]*
</details>

---

### Pregunta 58

**Una sede electrónica redirige con un 301 todo el tráfico HTTP hacia HTTPS. ¿Es suficiente?**

A) No: la primera petición aún viaja en claro y puede interceptarse, por lo que debe añadirse HSTS y, si es posible, la precarga
B) Sí: la redirección permanente garantiza que ninguna petición viaje sin cifrar
C) No, porque el código correcto para redirigir a HTTPS es el 403

<details><summary>Respuesta</summary>

**Correcta: A) No: la primera petición aún viaja en claro y puede interceptarse, por lo que debe añadirse HSTS y, si es posible, la precarga** **HSTS** (RFC 6797) obliga al navegador a usar siempre HTTPS con ese dominio, y la **precarga** aplica la protección **desde la primera visita**, eliminando el único momento de riesgo.

*Referencia: §5.2.1 [RFC6797]*
</details>

---

### Pregunta 59

**¿Qué medida del anexo II del Esquema Nacional de Seguridad se refiere específicamente a la protección de servicios y aplicaciones web?**

A) `mp.com.1`, perímetro seguro
B) `mp.s.2`, protección de servicios y aplicaciones web
C) `op.exp.10`, protección de claves criptográficas

<details><summary>Respuesta</summary>

**Correcta: B) `mp.s.2`, protección de servicios y aplicaciones web** Es exigible en las **tres categorías** y obliga ya en la BÁSICA a realizar auditorías **[R1 o R2]** —de caja negra o de caja blanca—, además de prevenir el escalado de privilegios y los ataques de secuencias de órdenes en sitios cruzados. En categoría ALTA se exigen `+R2 +R3`.

*Referencia: §6.1.1 [ENS]*
</details>

---

### Pregunta 60

**Conforme al artículo 38 de la Ley 40/2015, la sede electrónica se caracteriza porque:**

A) Puede ser gestionada por cualquier entidad privada en nombre de la Administración
B) Es equivalente al portal de internet regulado en el artículo 39
C) Su titularidad, gestión y administración corresponden a una Administración Pública u organismo público, y sus comunicaciones se realizan mediante certificados de sede electrónica

<details><summary>Respuesta</summary>

**Correcta: C) Su titularidad, gestión y administración corresponden a una Administración Pública u organismo público, y sus comunicaciones se realizan mediante certificados de sede electrónica** Además está sujeta a los principios de transparencia, publicidad, responsabilidad, calidad, seguridad, disponibilidad, accesibilidad, neutralidad e interoperabilidad. El **portal de internet** del art. 39 no tiene ese régimen reforzado.

*Referencia: §6.1.1 [L40-2015]*
</details>
