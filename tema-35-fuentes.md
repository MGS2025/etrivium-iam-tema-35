# Tema 35 — Fuentes

> **Título oficial**: Internet: arquitectura de red. Origen, evolución y estado actual. Principales servicios. Protocolos HTTP, HTTPS y SSL/TLS.
>
> **Criterio de cita**: en el contenido, las especificaciones técnicas se citan **por su número de RFC** (p. ej. «RFC 9110») y las normas jurídicas por su denominación oficial; el registro completo, con el identificador breve que usan el test y los diagramas (`[RFC9110]`, `[ENS]`, `[ICANN]`), está en este documento. **Tier 1** = normativa española y europea directamente aplicable y especificaciones de estándares abiertos (IETF, ISO/IEC, W3C, ICANN). **Tier 2** = informes de medición, estadísticas oficiales de organismos gestores y documentación histórica de referencia, citados para cuantificar el «estado actual». **Tier 3** = marco municipal de contexto.
>
> **Verificación**: **el número, el título, la fecha, el estado y las relaciones de obsolescencia de todos los RFC citados se han contrastado contra el índice oficial del RFC Editor** (`rfc-index.txt`), no de memoria. De ahí procede, entre otros, el dato de que el RFC 8446 ha sido **obsoletado por el RFC 9846 en julio de 2026**. Las medidas del anexo II del ENS se han contrastado contra el **PDF oficial del BOE** (BOE-A-2022-7191). Las cifras del estado actual se han verificado en la fuente que las publica, con la fecha indicada en cada caso.

---

## Tier 1 — Normativa y estándares

### Normativa española y europea

| ID | Referencia |
|---|---|
| `[ENS]` | Real Decreto **311/2022, de 3 de mayo**, por el que se regula el **Esquema Nacional de Seguridad** (BOE núm. 106, de 4 de mayo de 2022). En este tema se citan, verificadas contra el PDF del BOE: el art. 20 (mínimo privilegio y configuración de seguridad), el art. 22 y, del **anexo II**, las medidas **`mp.com.1`** (perímetro seguro), **`mp.com.2`** (protección de la confidencialidad), **`mp.com.3`** (protección de la integridad y de la autenticidad), **`mp.com.4`** (separación de flujos de información en la red), **`mp.s.1`** (protección del correo electrónico), **`mp.s.2`** (protección de servicios y aplicaciones web), **`mp.s.3`** (protección de la navegación web), **`mp.s.4`** (protección frente a la denegación de servicio), **`mp.si.2`** (criptografía), **`mp.eq.4`**, **`op.acc.4`**, **`op.acc.5`**, **`op.acc.6`** y **`op.exp.10`** (protección de claves criptográficas). |
| `[CCN-STIC-807]` | Centro Criptológico Nacional. *CCN-STIC-807: Criptología de empleo en el ENS*. Fija los **algoritmos y parámetros criptográficos autorizados** y sus longitudes de clave por nivel; es la guía a la que remiten `mp.com.2.r1` y `mp.com.3.r2`. Es la referencia correcta en un pliego, en lugar de congelar un número de RFC. |
| `[CCN-STIC-500]` | Centro Criptológico Nacional. Guías de **bastionado** de las series 500 y 600 (configuración segura por tecnología: servidores web, servidores de correo, DNS, SSH), exigidas por `op.exp.2` y por el art. 20.d del ENS. |
| `[L39-2015]` | Ley **39/2015, de 1 de octubre**, del Procedimiento Administrativo Común de las Administraciones Públicas. Derecho a relacionarse electrónicamente y obligación para las personas jurídicas (art. 14), sistemas de **identificación** (art. 9) y de **firma** (art. 10) y registro electrónico (art. 16). |
| `[L40-2015]` | Ley **40/2015, de 1 de octubre**, de Régimen Jurídico del Sector Público. **Art. 38 (sede electrónica)**: titularidad, gestión y administración de una Administración Pública, principios aplicables y comunicaciones mediante **certificado de sede electrónica**; **art. 39** (portal de internet); arts. 40-43 (sello electrónico y **CSV**); art. 41 (actuación administrativa automatizada); y **art. 156**, fundamento legal del ENI y del ENS. |
| `[RD203-2021]` | Real Decreto **203/2021, de 30 de marzo**, Reglamento de actuación y funcionamiento del sector público por medios electrónicos: sede electrónica y sede asociada, punto de acceso general electrónico, CSV y archivo electrónico único. |
| `[ENI]` | Real Decreto **4/2010, de 8 de enero**, por el que se regula el **Esquema Nacional de Interoperabilidad**, y sus **Normas Técnicas de Interoperabilidad**. Principio de **neutralidad tecnológica** y uso de estándares abiertos, relevante para la publicación de servicios en doble pila y para los formatos. Ver Tema 39. |
| `[RGPD]` | Reglamento (UE) **2016/679**, General de Protección de Datos. Art. 5.1.f (integridad y confidencialidad), art. **32** (seguridad del tratamiento) y arts. **33 y 34** (notificación de violaciones de seguridad: **72 horas**). |
| `[LOPDGDD]` | Ley Orgánica **3/2018, de 5 de diciembre**, de Protección de Datos Personales y garantía de los derechos digitales. |
| `[LSSI]` | Ley **34/2002, de 11 de julio**, de servicios de la sociedad de la información y de comercio electrónico. **Art. 22.2**: consentimiento para el uso de **cookies** no imprescindibles, con la AEPD como autoridad competente. |
| `[RD1112-2018]` | Real Decreto **1112/2018, de 7 de septiembre**, sobre **accesibilidad** de los sitios web y aplicaciones para dispositivos móviles del sector público (transposición de la Directiva (UE) 2016/2102). Norma **UNE-EN 301 549** y **declaración de accesibilidad** obligatoria. |
| `[NIS2]` | Directiva (UE) **2022/2555**, relativa a las medidas destinadas a garantizar un elevado nivel común de **ciberseguridad** en la Unión. |
| `[EIDAS2]` | Reglamento (UE) **2024/1183**, que modifica el Reglamento (UE) 910/2014 en lo relativo al **marco europeo de identidad digital**. Su **art. 45** y el anexo IV regulan los **certificados cualificados de autenticación de sitio web (QWAC)** y su reconocimiento por los navegadores; desarrollo técnico en la **ETSI TS 119 411-5** (modelos 1-QWAC y 2-QWAC). |

### Especificaciones del IETF (RFC)

| ID | Referencia |
|---|---|
| `[RFC-ED]` | **RFC Editor**, *rfc-index*, y **RFC 2026** (proceso de estandarización) y **RFC 6410** (reducción a dos escalones: *Proposed Standard* e *Internet Standard*). Reglas de la serie: numeración inmutable, relaciones *obsoletes* y *updates*, categorías y serie **STD**. |
| `[RFC801]` | *NCP/TCP Transition Plan* (1981). Documento del plan de migración de ARPANET que fija el **1 de enero de 1983** como fecha de corte. |
| `[CERF-KAHN]` | V. Cerf y R. Kahn, *A Protocol for Packet Network Intercommunication*, IEEE Transactions on Communications (**1974**). Origen del protocolo TCP y de los principios de diseño de la interconexión de redes. |
| `[RFC1122]` | *Requirements for Internet Hosts — Communication Layers* (1989), y **RFC 1123**. Definición canónica del modelo **TCP/IP de cuatro capas** y ubicación de ARP. |
| `[RFC791]` | *Internet Protocol* (1981) y **RFC 792 (ICMP)**. Especificación de IPv4. |
| `[RFC8200]` | *Internet Protocol, Version 6 (IPv6) Specification* (julio de 2017, **STD 86**). Obsoleta el RFC 2460. Cabecera fija de 40 bytes, cabeceras de extensión, sin suma de control y fragmentación solo en el origen. |
| `[RFC4291]` | *IP Version 6 Addressing Architecture*. Tipos de dirección: unidifusión global, enlace local `fe80::/10`, únicas locales `fc00::/7`, multidifusión `ff00::/8` y anycast. |
| `[RFC1918]` | *Address Allocation for Private Internets* (**BCP 5**). Rangos **10.0.0.0/8**, **172.16.0.0/12** y **192.168.0.0/16**. |
| `[RFC6598]` | *IANA-Reserved IPv4 Prefix for Shared Address Space*. Rango **100.64.0.0/10** para **CGNAT**. |
| `[RFC4632]` | *Classless Inter-domain Routing (CIDR)*. Supresión del direccionamiento con clases y agregación de rutas. |
| `[RFC3022]` | *Traditional IP Network Address Translator (Traditional NAT)*. NAT y PAT. |
| `[RFC6146]` | *Stateful NAT64* y **RFC 6147 (DNS64)**; **RFC 6877 (464XLAT)**. Traducción entre IPv6 e IPv4. El antiguo **NAT-PT** (RFC 2766) fue declarado **histórico** por el **RFC 4966**. |
| `[RFC6724]` | *Default Address Selection for IPv6* y **RFC 8305 (Happy Eyeballs v2)**. Selección de protocolo en entornos de doble pila. |
| `[RFC4271]` | *A Border Gateway Protocol 4 (BGP-4)*. Único protocolo de encaminamiento **exterior** de Internet; funciona sobre **TCP/179** y es de **vector de caminos**. |
| `[RFC1034]` | *Domain Names — Concepts and Facilities* (noviembre de 1987). Jerarquía, delegación, zonas, resolución **recursiva** e **iterativa** y caché con TTL. |
| `[RFC1035]` | *Domain Names — Implementation and Specification* (noviembre de 1987). Formato de mensaje, tipos de registro, puerto **53**, uso de UDP y TCP y transferencias de zona. |
| `[RFC6891]` | *Extension Mechanisms for DNS (EDNS(0))*. Supera el límite histórico de 512 bytes del mensaje DNS por UDP. |
| `[RFC4033]` | *DNS Security Introduction and Requirements*, y **RFC 4034 y 4035**. **DNSSEC**: firma de los datos de la zona y cadena de confianza desde la raíz. |
| `[RFC7858]` | *Specification for DNS over Transport Layer Security (TLS)*. **DoT**, puerto **TCP 853**. |
| `[RFC8484]` | *DNS Queries over HTTPS (DoH)*. Puerto **443**. |
| `[RFC8659]` | *DNS Certification Authority Authorization (CAA) Resource Record*. Limita qué AC puede emitir certificados para un dominio. |
| `[RFC5321]` | *Simple Mail Transfer Protocol*. **SMTP**: envío y tránsito del correo. |
| `[RFC1939]` | *Post Office Protocol — Version 3* (**STD 53**). **POP3**. |
| `[RFC9051]` | *Internet Message Access Protocol (IMAP) — Version 4rev2* (2021). Obsoleta el RFC 3501. |
| `[RFC8314]` | *Cleartext Considered Obsolete: Use of TLS for Email Submission and Access*. Recomienda **TLS implícito** (465, 993, 995) frente a STARTTLS. |
| `[RFC2045]` | *MIME (Multipurpose Internet Mail Extensions)*, RFC 2045 a 2049. Adjuntos, juegos de caracteres y codificación **Base64**. |
| `[RFC7208]` | *Sender Policy Framework (SPF) for Authorizing Use of Domains in Email, Version 1*. |
| `[RFC6376]` | *DomainKeys Identified Mail (DKIM) Signatures* (**STD 76**). |
| `[RFC9989]` | *Domain-Based Message Authentication, Reporting, and Conformance (DMARC)* (**mayo de 2026**), junto con el **RFC 9990** (informes agregados) y el **RFC 9991** (informes de fallo). **Obsoletan el RFC 7489**, que era *Informational*, y elevan DMARC a *Standards Track*. |
| `[RFC8461]` | *SMTP MTA Strict Transport Security (MTA-STS)*. Exige TLS en el correo saliente hacia los dominios que lo declaran. |
| `[RFC959]` | *File Transfer Protocol (FTP)* (1985). Canal de **control (21)** y de **datos (20)**; modos **activo** y **pasivo**. |
| `[RFC4251]` | *The Secure Shell (SSH) Protocol Architecture*, y **RFC 4252** (autenticación), **RFC 4253** (transporte) y **RFC 4254** (conexión). **Puerto TCP 22**; base de **SFTP** y **SCP**. |
| `[RFC2131]` | *Dynamic Host Configuration Protocol*. **DHCP**: intercambio **DORA**, puertos **UDP 67 y 68**, concesiones y temporizadores T1 y T2. |
| `[RFC9915]` | *Dynamic Host Configuration Protocol for IPv6 (DHCPv6)* (**enero de 2026**, **STD 102**). **Obsoleta el RFC 8415**. Puertos **UDP 547 y 546**. |
| `[RFC4862]` | *IPv6 Stateless Address Autoconfiguration (SLAAC)*. Configuración **sin estado** a partir de los anuncios del encaminador. |
| `[RFC9110]` | *HTTP Semantics* (junio de 2022, **STD 97**). **Obsoleta los RFC 2818, 7230-7235, 7538, 7615 y 7694**. Métodos y sus propiedades de **seguridad** e **idempotencia**, códigos de estado, cabeceras y definición de **HTTPS** (§4.2.2). |
| `[RFC9111]` | *HTTP Caching* (**STD 98**). Directivas `Cache-Control`, validación condicional con `ETag` y `Last-Modified`, y respuesta **304**. |
| `[RFC9112]` | *HTTP/1.1* (**STD 99**). Sintaxis del mensaje, conexiones persistentes y transferencia por trozos. |
| `[RFC9113]` | *HTTP/2*. Protocolo binario, multiplexación de corrientes, compresión **HPACK** (**RFC 7541**) y priorización. |
| `[RFC9114]` | *HTTP/3*. HTTP sobre **QUIC**, con compresión **QPACK** (**RFC 9204**). |
| `[RFC9000]` | *QUIC: A UDP-Based Multiplexed and Secure Transport* (2021), con **RFC 9001** (uso de TLS en QUIC) y **RFC 9002** (detección de pérdidas y control de congestión). Establecimiento **1-RTT** y **0-RTT**, y **migración de conexión**. |
| `[RFC6265]` | *HTTP State Management Mechanism*. Cookies y atributos `Secure`, `HttpOnly`, `SameSite`, `Domain`, `Path`, `Expires` y `Max-Age`. |
| `[RFC3986]` | *Uniform Resource Identifier (URI): Generic Syntax*. Esquema, autoridad, ruta, consulta y fragmento. |
| `[RFC7301]` | *Transport Layer Security (TLS) Application-Layer Protocol Negotiation Extension (ALPN)*. Mecanismo por el que se negocia HTTP/2 dentro del saludo TLS. |
| `[RFC9846]` | *The Transport Layer Security (TLS) Protocol Version 1.3* (**julio de 2026**). **Obsoleta los RFC 8446 (TLS 1.3), 5246 (TLS 1.2), 5077, 6961, 7627 y 8422** y actualiza los RFC 5705 y 6066. Unifica la especificación y añade requisitos para las implementaciones de TLS 1.2. **Es la referencia vigente de TLS.** |
| `[RFC8446]` | *The Transport Layer Security (TLS) Protocol Version 1.3* (agosto de 2018). Versión histórica, **obsoletada por el RFC 9846**; se conserva la cita por ser la que recogen la mayoría de los temarios y la bibliografía. |
| `[RFC8996]` | *Deprecating TLS 1.0 and TLS 1.1* (2021). Declara **obsoletas** ambas versiones. |
| `[RFC7568]` | *Deprecating Secure Sockets Layer Version 3.0* (2015), y **RFC 6176** para SSL 2.0. **Prohíben** el uso de SSL. |
| `[RFC6797]` | *HTTP Strict Transport Security (HSTS)*. Cabecera `Strict-Transport-Security` y lista de **precarga**. |
| `[RFC5280]` | *Internet X.509 Public Key Infrastructure Certificate and CRL Profile*. Perfil del certificado **X.509 v3**, extensiones (**`subjectAltName`**, `keyUsage`, `basicConstraints`), validación de la **ruta de certificación** y **CRL**. |
| `[RFC6960]` | *X.509 Internet PKI Online Certificate Status Protocol (OCSP)*. Respuestas `good`, `revoked` y `unknown`; el **grapado** se define en la extensión `status_request` del **RFC 6066**. |
| `[RFC6962]` | *Certificate Transparency*. Registros públicos y auditables de los certificados emitidos. |

### Otros estándares

| ID | Referencia |
|---|---|
| `[ISO7498]` | **ISO/IEC 7498-1**. *Modelo de referencia OSI*: siete capas, servicios y unidades de datos. |
| `[W3C]` | **World Wide Web Consortium**. Estándares de la Web: **HTML**, **CSS**, **DOM**, **XML**, **RDF**, **OWL** y **SPARQL** (Web Semántica) y las pautas de accesibilidad **WCAG**. Fundado por **Tim Berners-Lee** en octubre de 1994. |
| `[IEEE802]` | **IEEE 802**. Normas de las capas física y de enlace: **802.3** (Ethernet) y **802.11** (Wi-Fi), y **802.1X** (control de acceso a la red por puerto). |
| `[FIPS203]` | NIST. **FIPS 203 (ML-KEM)**, base del intercambio híbrido **X25519MLKEM768** empleado hoy en TLS. Su integración en TLS 1.3 se especifica en `draft-ietf-tls-ecdhe-mlkem`, aprobado y **pendiente de publicación como RFC en agosto de 2026**; el valor asignado por la IANA es **4588 (`0x11EC`)**. |

---

## Tier 2 — Informes, estadísticas y documentación de referencia

| ID | Referencia |
|---|---|
| `[FNC]` | **Federal Networking Council**, resolución de **24 de octubre de 1995**, con la definición oficial del término «Internet»: espacio de direcciones único basado en IP, comunicaciones con TCP/IP y servicios de alto nivel superpuestos. |
| `[LEINER]` | B. Leiner, V. Cerf, D. Clark, R. Kahn, L. Kleinrock, D. Lynch, J. Postel, L. Roberts y S. Wolff, *Brief History of the Internet* (Internet Society). Relato de los protagonistas; desmiente expresamente el mito del origen antinuclear de ARPANET. |
| `[ICANN]` | **ICANN**. Modelo de múltiples partes interesadas, funciones **IANA** y su transición a **PTI** el **1 de octubre de 2016**, tras la expiración del contrato con la NTIA el 30 de septiembre de 2016; sistema de servidores raíz (**13 identidades**) y **RSSAC**. |
| `[RIPE]` | **RIPE NCC**. Registro regional de Europa, Oriente Medio y Asia Central. Agotamiento de IPv4: fase del **último `/8`** desde el **14 de septiembre de 2012** (una única asignación de `/22` por operador) y **agotamiento pleno el 25 de noviembre de 2019**, con lista de espera para direcciones recuperadas. La IANA había agotado su reserva libre el **3 de febrero de 2011**. |
| `[IETF]` | **IETF**. Estructura (grupos de trabajo, áreas, **IESG**, **IAB**, **IRTF**), funcionamiento por consenso aproximado y proceso de publicación de los RFC. |
| `[ITU2025]` | **UIT**, *Measuring Digital Development: Facts and Figures 2025* (noviembre de 2025). **≈ 6.000 millones** de personas usuarias de Internet (**74 %** de la población mundial), **2.200 millones** sin conexión (26 %), y brechas por renta, sexo y ámbito urbano-rural. |
| `[GOOGLE-IPV6]` | **Google**, *IPv6 Statistics*. Adopción medida sobre el acceso a los servicios de Google: supera el **50 %** por primera vez el **28 de marzo de 2026** (50,10 %). España se sitúa en torno al **10 %**. |
| `[CIDR]` | **CIDR Report** y mediciones de **APNIC**. Tamaño de la tabla global de encaminamiento: **más de 1.000.000** de prefijos IPv4 y ≈ **250.000** de IPv6; ≈ **80.000** sistemas autónomos activos (2026). |
| `[W3TECHS]` | **W3Techs**. Adopción de HTTP/3: ≈ **39,5 %** de los sitios lo anuncian (junio de 2026). La cifra mide **anuncio** (`Alt-Svc` o registro DNS HTTPS), no peticiones efectivamente servidas. |
| `[CHROME-TR]` | **Google**, *HTTPS encryption on the web* (Transparency Report). **Más del 95 %** de las cargas de página en Chrome de escritorio y **más del 97 %** en Android se realizan por HTTPS (2026). |
| `[CABF]` | **CA/Browser Forum**, *Ballot SC-081v3* (abril de 2025). Calendario de reducción de la validez máxima de los certificados TLS públicos: **200 días desde el 15-3-2026**, **100 días desde el 15-3-2027** y **47 días desde el 15-3-2029**, con reducción paralela de los periodos de reutilización de datos de validación. |
| `[LE-OCSP]` | **Let's Encrypt**. Fin del servicio **OCSP el 6 de agosto de 2025** por motivos de privacidad, sustitución por **CRL** y emisión de certificados de **seis días** de validez. |
| `[ESPANIX]` | **ESPANIX** (constituido el **13 de mayo de 1997**) y **DE-CIX Madrid** (2016). Puntos neutros españoles: ESPANIX registra picos por encima de **2 Tbps** con un crecimiento superior al 12 % interanual en 2026, y DE-CIX Madrid supera **1,5 Tbit/s**. |
| `[DOMINIOS-ES]` | **Red.es · Dominios.es**. Registro del ccTLD `.es`: **2.226.598** dominios registrados a **6 de agosto de 2026**. |
| `[DNSSEC-STATS]` | Estadísticas de despliegue de **DNSSEC** en la raíz: **1.348 de 1.437** dominios de primer nivel firmados (≈ **93,8 %**) a julio de 2026, frente a una adopción muy minoritaria en los dominios de segundo nivel. |
| `[ROOT-SERVERS]` | **root-servers.org** y RSSAC. **13 identidades** (A-M) operadas por **12 organizaciones**, desplegadas mediante **anycast** en más de **2.000 instancias** operativas (agosto de 2026). |
| `[MANRS]` | **MANRS** (*Mutually Agreed Norms for Routing Security*) y **RPKI** (RFC 6480 y siguientes), con objetos **ROA**. Contramedidas frente al secuestro de prefijos BGP y las fugas de rutas. |
| `[OWASP]` | **OWASP**, *Top 10*. Catálogo de riesgos de las aplicaciones web al que responden las cabeceras de seguridad y los atributos de cookie tratados en §4.2.2. Desarrollado en los Temas 23 y 25. |

---

## Tier 3 — Contexto municipal

| ID | Referencia |
|---|---|
| `[MADRID-SEDE]` | **Ayuntamiento de Madrid**, sede electrónica `sede.madrid.es` y portal `madrid.es`. Supuesto de referencia empleado en todo el tema y en los tres casos prácticos. |
| `[BOAM-10032]` | **BOAM núm. 10.032**, bases específicas de la convocatoria de Técnico Auxiliar de Informática del Ayuntamiento de Madrid. Enunciado oficial del Tema 35 y de los temas con los que limita (33, 34, 36, 37 y 39). |
| `[SARA]` | **Red SARA** y **Punto de Acceso General electrónico**. Infraestructura de interconexión de las Administraciones españolas, alternativa a la transferencia directa de ficheros entre organismos. |

---

## Fuentes consultadas y NO utilizadas

- **Bibliografía académica de redes** (Tanenbaum, Kurose y Ross, Stevens): excelente para el fundamento, pero **desactualizada** en lo que este tema tiene de volátil (HTTP/3, TLS 1.3 reeditado, cifras de adopción). Se ha preferido la especificación primaria.
- **Blogs y portales divulgativos** sobre TLS, DNS o IPv6: útiles para localizar hechos, pero **no citados como fuente**; todo dato tomado de ellos se ha contrastado después contra el RFC, el BOE o el organismo que lo publica.
- **Documentación de fabricante** (servidores web, cortafuegos, suites de correo): descartada deliberadamente para no atar el tema a un producto concreto, siguiendo el criterio del resto de la serie técnica.
