# Tema 35 — Índice

> **Título oficial**: Internet: arquitectura de red. Origen, evolución y estado actual. Principales servicios. Protocolos HTTP, HTTPS y SSL/TLS.
>
> **Bloque**: Parte II — Técnico (Temas 11-40)
> **Nivel**: C1 — Técnico Auxiliar TIC, Ayuntamiento de Madrid

---

## Estructura del tema

1. **Origen, evolución y estado actual de Internet**
   1.1. Origen e historia de Internet
   1.1.1. De ARPANET a la consolidación de la pila TCP/IP
   1.1.2. Evolución de la World Wide Web y estado actual
   1.2. Gobernanza de Internet y estandarización
   1.2.1. Organismos internacionales de regulación
   1.2.2. Proceso de estandarización técnica y documentos RFC

2. **Arquitectura de red de Internet**
   2.1. Modelo de comunicación TCP/IP
   2.1.1. Pila TCP/IP y correspondencia con el modelo OSI
   2.1.2. Encapsulamiento y transmisión de datos
   2.2. Infraestructura y direccionamiento
   2.2.1. Sistemas Autónomos y puntos de intercambio de tráfico
   2.2.2. Coexistencia de los protocolos IPv4 e IPv6
   2.2.3. Sistema de Nombres de Dominio

3. **Principales servicios de Internet**
   3.1. Servicios de la capa de aplicación
   3.1.1. Correo electrónico y sus protocolos
   3.1.2. Transferencia de archivos
   3.2. Servicios de gestión y red
   3.2.1. Acceso remoto seguro
   3.2.2. Configuración dinámica de red

4. **Protocolo HTTP**
   4.1. Fundamentos y versiones del protocolo HTTP
   4.1.1. Modelo cliente-servidor y comunicación sin estado
   4.1.2. Evolución desde HTTP/1.1 hasta HTTP/3
   4.2. Mensajes HTTP y mecanismos de estado
   4.2.1. Estructura de mensajes, métodos y códigos de respuesta
   4.2.2. Cabeceras HTTP, cookies y sesiones

5. **Protocolos SSL/TLS y HTTPS**
   5.1. Protocolos de seguridad SSL y TLS
   5.1.1. Arquitectura, subprotocolos y negociación TLS
   5.1.2. Criptografía, certificados digitales e infraestructura PKI
   5.2. Protocolo HTTPS
   5.2.1. Funcionamiento de HTTP sobre TLS

6. **Seguridad y normativa en la Administración Pública (material complementario)**
   6.1. Requisitos de seguridad en servicios web públicos
   6.1.1. Esquema Nacional de Seguridad y sedes electrónicas

---

## Conceptos clave para memorizar

| Concepto | Dato clave |
|---|---|
| Fechas fundacionales | **1969**: primeros cuatro nodos de ARPANET (UCLA, SRI, UCSB, Utah). **1974**: artículo de **Cerf y Kahn** con el protocolo TCP. **1-1-1983**: *flag day* — ARPANET abandona NCP y adopta **TCP/IP**; es la fecha de nacimiento de Internet tal como se entiende hoy. **1989-1991**: **Berners-Lee** propone y publica la **World Wide Web** en el **CERN**. **1993**: navegador **Mosaic**. **30-4-1993**: el CERN libera la Web al dominio público |
| Internet ≠ Web | **Internet** es la infraestructura (red de redes con TCP/IP); la **Web** es **un servicio más** que se ejecuta sobre ella, junto al correo, DNS, FTP o SSH. Confundirlas es el error conceptual más penalizado del tema |
| Gobernanza: quién hace qué | **ICANN** (con la **IANA**, operada desde 2016 por la **PTI**) gestiona identificadores únicos: nombres, números y parámetros de protocolo. **IETF** elabora los estándares (RFC). **IAB** supervisa la arquitectura; **IRTF**, la investigación. **ISOC** es el paraguas institucional. **W3C** estandariza la **Web** (HTML, CSS), **no** Internet. **IEEE** normaliza las capas físicas (802.3, 802.11) |
| Transición IANA | El contrato del Departamento de Comercio de EE. UU. sobre las funciones IANA **expiró el 30-9-2016**; desde el **1-10-2016** las ejerce **PTI**, filial de ICANN, bajo modelo de **múltiples partes interesadas** (*multistakeholder*) |
| Los cinco RIR | **ARIN** (Norteamérica) · **RIPE NCC** (Europa, Oriente Medio y Asia Central) · **APNIC** (Asia-Pacífico) · **LACNIC** (Latinoamérica y Caribe) · **AFRINIC** (África). España pertenece a **RIPE NCC**. Reparten direcciones a los **LIR** (operadores) |
| Serie RFC | Publica el **RFC Editor**. Un documento nace como **Internet-Draft** (caduca a los **6 meses**), y si prospera se publica como RFC con **número inmutable**: no se modifica, se **obsoleta** (*obsoletes*) o se **actualiza** (*updates*). Categorías: *Standards Track* (**Proposed Standard** → **Internet Standard**, con serie **STD**), *Informational*, *Experimental*, *Historic* y *Best Current Practice* (**BCP**) |
| Pila TCP/IP | **Cuatro** capas: **acceso a red / enlace**, **internet**, **transporte** y **aplicación**. OSI tiene **siete**. Correspondencia: la capa de aplicación de TCP/IP absorbe **aplicación + presentación + sesión** de OSI; la de acceso a red, **enlace + física** |
| PDU por capa | Aplicación → **mensaje** · Transporte → **segmento** (TCP) o **datagrama** (UDP) · Internet → **paquete** o datagrama IP · Enlace → **trama** · Física → **bit** |
| TCP vs UDP | **TCP**: orientado a conexión (**saludo en tres pasos**: SYN, SYN-ACK, ACK), fiable, ordenado, con control de flujo y congestión. **UDP**: sin conexión, sin garantías, **cabecera de 8 bytes** frente a los **20** mínimos de TCP. HTTP/3 corre sobre **UDP** porque QUIC reimplementa la fiabilidad en espacio de usuario |
| Sistema Autónomo (AS) | Conjunto de redes con una **política de encaminamiento única** bajo una administración común, identificado por un **ASN** de **32 bits** (antes 16). El protocolo que los une es **BGP-4** (RFC 4271), **TCP/179**, único protocolo de encaminamiento **exterior** de Internet. Hay ≈ **80.000 AS** activos |
| Tránsito, *peering* e IXP | **Tránsito**: se paga a un operador superior para llegar a *todo* Internet. **Peering**: intercambio directo, normalmente **sin coste**, solo del tráfico propio y de los clientes de ambos. Un **IXP** (punto neutro) es la infraestructura donde ese intercambio se hace masivamente: en España, **ESPANIX** y **DE-CIX Madrid** |
| Agotamiento de IPv4 | **IANA** agotó su reserva libre el **3-2-2011**; **RIPE NCC** entró en fase de agotamiento el **25-11-2019**. Paliativos: **CIDR** (RFC 4632), **direccionamiento privado** (RFC 1918: 10/8, 172.16/12, 192.168/16), **NAT/PAT** y **CGNAT** (RFC 6598: 100.64.0.0/10). Ninguno resuelve el problema: solo lo aplaza |
| IPv4 vs IPv6 | **IPv4**: 32 bits, ≈ 4.294 millones de direcciones, notación decimal con puntos, cabecera **variable (20-60 bytes)**, con suma de control. **IPv6** (RFC 8200): **128 bits**, notación hexadecimal con dos puntos, cabecera **fija de 40 bytes**, **sin suma de control**, **sin fragmentación en tránsito** (la hace el origen), **sin difusión** (*broadcast*): usa **multidifusión** y **anycast**. Prefijo estándar de subred: **/64** |
| Mecanismos de transición | **Doble pila** (*dual stack*, el recomendado) · **túneles** (6in4, 6to4, Teredo, GRE) · **traducción** (NAT64/DNS64, 464XLAT). **Nunca** hay traducción directa IPv4↔IPv6 sin pasarela: son protocolos **incompatibles** |
| DNS: jerarquía | **Raíz** (`.`) → **TLD** (gTLD, ccTLD como `.es`) → dominio de segundo nivel → subdominios. **13 identidades** de servidor raíz (A-M) sobre **más de 2.000 instancias** con **anycast**. Puerto **53** (UDP para consultas, **TCP** para respuestas grandes y transferencias de zona **AXFR**) |
| Resolución DNS | El cliente hace una consulta **recursiva** al resolutor; el resolutor hace consultas **iterativas** a raíz, TLD y servidor autoritativo. Registros: **A** (IPv4), **AAAA** (IPv6), **CNAME** (alias), **MX** (correo), **NS**, **PTR** (inverso), **TXT**, **SOA**, **SRV**, **CAA** (qué AC puede emitir certificados) |
| Seguridad del DNS | **DNSSEC** (RFC 4033-4035) **firma** las respuestas: aporta **autenticidad e integridad**, **no confidencialidad**. **DoT** (RFC 7858, **TCP/853**) y **DoH** (RFC 8484, **HTTPS/443**) cifran la consulta: aportan **confidencialidad**, no autenticidad de la zona. Son complementarios, no alternativos |
| Correo: puertos | **SMTP** entre servidores: **25**. **Envío desde el cliente** (*submission*): **587** con STARTTLS o **465** con TLS implícito. **POP3**: 110 · **POP3S**: 995. **IMAP**: 143 · **IMAPS**: 993. El **RFC 8314** desaconseja el texto en claro y recomienda **TLS implícito** |
| Autenticación del remitente | **SPF** (RFC 7208, registro TXT con los emisores autorizados) · **DKIM** (RFC 6376, **firma criptográfica** de la cabecera y el cuerpo) · **DMARC** (política de alineamiento y de informes; reeditado en **mayo de 2026** por los **RFC 9989, 9990 y 9991**, que obsoletan el RFC 7489) |
| FTP | **RFC 959**, dos canales: **control TCP/21** y **datos TCP/20**. **Modo activo**: el servidor abre la conexión de datos hacia el cliente (lo bloquean los cortafuegos). **Modo pasivo**: la abre el cliente. **FTPS** = FTP sobre TLS; **SFTP** = subsistema de **SSH** (puerto **22**), no tiene nada que ver con FTP |
| SSH | **Puerto 22**, RFC 4251-4254. Tres capas: **transporte** (cifrado e integridad), **autenticación** y **conexión** (canales multiplexados). Sustituye a **Telnet (23)**, `rlogin` y `rsh`, que van en claro. Permite **túneles** y reenvío de puertos |
| DHCP | **RFC 2131**, puertos **UDP 67** (servidor) y **68** (cliente). Intercambio **DORA**: *Discover* → *Offer* → *Request* → *Acknowledge*. En IPv6 conviven **SLAAC** (autoconfiguración sin estado) y **DHCPv6** (**UDP 546/547**), reeditado en enero de 2026 como **RFC 9915 (STD 102)** |
| HTTP: naturaleza | Protocolo de **capa de aplicación**, **cliente-servidor**, **sin estado** (*stateless*) y **sin conexión** en su semántica. Puerto **80**; sobre TLS, **443**. La especificación vigente está en los **RFC 9110-9112** (junio de 2022, **STD 97, 98 y 99**), que sustituyen a los RFC 723x y al RFC 2616 |
| Versiones de HTTP | **0.9** (1991, solo `GET`) · **1.0** (RFC 1945, 1996) · **1.1** (1997; **conexiones persistentes**, `Host` obligatorio, *pipelining*) · **2** (RFC 9113: **binario**, **multiplexado**, **HPACK**, *server push*) · **3** (RFC 9114: sobre **QUIC/UDP**, cifrado obligatorio, **QPACK**, elimina el bloqueo de cabecera de línea del transporte) |
| Métodos HTTP | **Seguros** (no modifican): `GET`, `HEAD`, `OPTIONS`, `TRACE`. **Idempotentes** (repetirlos da el mismo resultado): los seguros más `PUT` y `DELETE`. **`POST` no es ni seguro ni idempotente**; **`PATCH` tampoco es idempotente** |
| Códigos de estado | **1xx** informativo · **2xx** éxito (200 OK, 201 Created, 204 No Content) · **3xx** redirección (**301** permanente, **302/307** temporal, **304** no modificado) · **4xx** error del **cliente** (400, **401** no autenticado, **403** no autorizado, 404, 429) · **5xx** error del **servidor** (500, 502, **503** no disponible, 504) |
| Cookies | **RFC 6265**. Cabecera `Set-Cookie` del servidor y `Cookie` del cliente. Atributos de seguridad: **`Secure`** (solo por HTTPS), **`HttpOnly`** (invisible para JavaScript, mitiga XSS), **`SameSite`** (mitiga CSRF) y `Expires`/`Max-Age` (de sesión frente a persistente) |
| SSL vs TLS | **SSL** es el nombre histórico de Netscape (1994-1996); **TLS** es su continuación en el IETF desde **1999**. **SSL 2.0 y 3.0 están prohibidos** (RFC 6176 y **RFC 7568**); **TLS 1.0 y 1.1**, declarados obsoletos por el **RFC 8996** (2021). Vigentes: **TLS 1.2 y TLS 1.3** |
| TLS 1.3 hoy | Publicado en **2018** como RFC 8446 y **reeditado en julio de 2026 como RFC 9846**, que **obsoleta tanto el RFC 8446 como el RFC 5246** (TLS 1.2) y unifica la especificación. Novedades de la versión 1.3: saludo en **1-RTT** (0-RTT en reanudación), **confidencialidad directa obligatoria**, solo cifrado **AEAD**, sin RSA estático, sin renegociación y sin compresión |
| Subprotocolos TLS | **Record** (el que transporta a todos los demás y aplica el cifrado) más **Handshake**, **Alert**, **Change Cipher Spec** (residual en 1.3, solo por compatibilidad con equipos intermedios) y los **datos de aplicación** |
| Certificados y revocación | **X.509 v3** (RFC 5280), emitido por una **AC**; validación por **cadena de confianza** hasta una raíz del almacén del navegador. Revocación por **CRL** o por **OCSP** (RFC 6960). Tendencia dominante: **certificados de vida corta**. Calendario del **CA/Browser Forum (SC-081v3)**: máximo **200 días desde el 15-3-2026**, **100 días desde el 15-3-2027** y **47 días desde el 15-3-2029** |
| HTTPS | No es un protocolo nuevo: es **HTTP transportado sobre TLS** en el puerto **443**. Orden correcto: **TCP → TLS → HTTP**. Protege el **cuerpo**, las **cabeceras**, las **cookies** y la **ruta** de la URL; **no oculta** la dirección IP de destino ni, salvo con ECH, el nombre del servidor en la extensión **SNI** |
| Refuerzos de HTTPS | **HSTS** (RFC 6797) obliga al navegador a usar siempre HTTPS · **CAA** limita qué AC puede emitir para el dominio · **CT** (transparencia de certificados) publica lo emitido en registros auditables · **ECH** cifra el nombre del servidor en el saludo |
| Servicios web en el ENS | **`mp.s.2` — Protección de servicios y aplicaciones web**, exigible en las **tres categorías** con **[R1 o R2]** (auditorías de caja negra o de caja blanca) desde la BÁSICA, y **+R2+R3** en la ALTA. **`mp.com.2`** protege la **confidencialidad** del canal y **`mp.com.3`** su **integridad y autenticidad**; **`mp.s.4`** cubre la **denegación de servicio** (desde nivel MEDIO de disponibilidad) |
| Sede electrónica | Regulada en el **art. 38 de la Ley 40/2015** y desarrollada por el **RD 203/2021**: titularidad, gestión y administración corresponden a una **Administración concreta**, y sus comunicaciones deben realizarse **mediante certificado de sede electrónica** que garantice identificación y comunicación segura. La del Ayuntamiento de Madrid es `sede.madrid.es` |
