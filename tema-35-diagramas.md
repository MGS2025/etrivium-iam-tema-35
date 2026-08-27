# Tema 35 — Catálogo de Diagramas

> **Título oficial**: Internet: arquitectura de red. Origen, evolución y estado actual. Principales servicios. Protocolos HTTP, HTTPS y SSL/TLS.
>
> **Versión**: v1.0
> **Fecha**: 2026-08-27
> **Autor**: ETRIVIUM
> **Formato**: SVG inline (zero-dependencias, escalable, imprimible, accesible con role/aria-label)
> **Paleta**: Ayuntamiento de Madrid #0055a0 (primario) + #d13c3c (alertas) + #2d8659 (ventajas) + #e89822 (callouts)
> **Nota técnica**: las clases CSS de cada SVG llevan sufijo numérico único (`.t1`, `.h1`…) para evitar colisiones de estilos entre los 18 diagramas embebidos en la misma página.

---

## Índice de diagramas

| ID | Título | Sección | Tipo | Formato |
|---|---|---|---|---|
| D1 | De ARPANET a la Internet actual: línea del tiempo | §1.1.1 | Línea temporal | 680×356 |
| D2 | Quién gobierna qué en Internet | §1.2.1 | Mapa de organismos | 680×372 |
| D3 | El camino de un estándar: del Internet-Draft al STD | §1.2.2 | Flujo + categorías | 680×356 |
| D4 | Pila TCP/IP frente al modelo OSI | §2.1.1 | Comparativa de capas | 680×372 |
| D5 | Encapsulamiento y desencapsulamiento | §2.1.2 | Estructura anidada | 680×352 |
| D6 | Internet como red de redes: AS, tránsito, *peering* e IXP | §2.2.1 | Topología | 680×372 |
| D7 | Agotamiento de IPv4 y mecanismos de coexistencia con IPv6 | §2.2.2 | Línea temporal + comparativa | 680×372 |
| D8 | DNS: jerarquía y resolución de un nombre paso a paso | §2.2.3 | Flujo numerado | 680×372 |
| D9 | Seguridad del DNS: qué resuelve DNSSEC y qué resuelven DoT y DoH | §2.2.3 | Comparativa | 680×340 |
| D10 | Correo electrónico: agentes, protocolos, puertos y autenticación | §3.1.1 | Flujo + tabla | 680×372 |
| D11 | FTP: modo activo, modo pasivo y alternativas seguras | §3.1.2 | Comparativa de flujos | 680×364 |
| D12 | SSH: arquitectura en tres capas y métodos de autenticación | §3.2.1 | Capas + tabla | 680×348 |
| D13 | DHCP: intercambio DORA y configuración en IPv6 | §3.2.2 | Secuencia | 680×364 |
| D14 | Anatomía de un mensaje HTTP: petición y respuesta | §4.2.1 | Estructura | 680×372 |
| D15 | De HTTP/0.9 a HTTP/3: qué resuelve cada versión | §4.1.2 | Evolución comparada | 680×372 |
| D16 | El estado en HTTP: cookies, sesiones y atributos de seguridad | §4.2.2 | Flujo + tabla | 680×356 |
| D17 | TLS: subprotocolos y saludo 1.2 frente a 1.3 | §5.1.1 | Arquitectura + secuencia | 680×372 |
| D18 | HTTPS de extremo a extremo en una sede electrónica | §5.2.1 · §6.1.1 | Flujo + validación | 680×380 |

---
## D1 · De ARPANET a la Internet actual: línea del tiempo

**Sección**: §1.1.1 — De ARPANET a la consolidación de la pila TCP/IP · §1.1.2
**Propósito**: Fijar en tres etapas las fechas que se preguntan literalmente, separando el nacimiento de la **red** (1969-1983) del nacimiento de la **Web** (1989-1993), que es la confusión más penalizada del tema.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 356" role="img" aria-label="Línea del tiempo de Internet en tres etapas: la red de investigación de 1969 a 1983 con ARPANET, el protocolo TCP de Cerf y Kahn y el día de la bandera de 1983; la etapa de la Web de 1983 a 1995 con el DNS, la World Wide Web del CERN, el navegador Mosaic y la privatización de NSFNET; y la etapa de madurez con el agotamiento de IPv4, HTTP dos y tres, TLS uno punto tres y la superación del cincuenta por ciento de IPv6 en 2026">
  <style>.t1{font:700 10.5px system-ui,sans-serif;fill:#fff}.s1{font:8.5px system-ui,sans-serif;fill:#fff}.d1{font:9px system-ui,sans-serif;fill:#333}.h1{font:700 13px system-ui,sans-serif;fill:#0055a0}.k1{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n1{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h1">Primero nace la RED (1983); la WEB llega seis años después</text>
  <text x="20" y="42" class="k1">ETAPA 1 · LA RED DE INVESTIGACIÓN</text>
  <rect x="20" y="50" width="154" height="58" rx="5" fill="#0055a0"/><text x="97" y="68" text-anchor="middle" class="t1">1969 · ARPANET</text><text x="97" y="83" text-anchor="middle" class="s1">4 nodos: UCLA, SRI,</text><text x="97" y="96" text-anchor="middle" class="s1">UCSB y Utah. Protocolo NCP</text>
  <rect x="182" y="50" width="154" height="58" rx="5" fill="#0055a0"/><text x="259" y="68" text-anchor="middle" class="t1">1974 · TCP</text><text x="259" y="83" text-anchor="middle" class="s1">Cerf y Kahn publican el</text><text x="259" y="96" text-anchor="middle" class="s1">protocolo de interconexión</text>
  <rect x="344" y="50" width="154" height="58" rx="5" fill="#0055a0"/><text x="421" y="68" text-anchor="middle" class="t1">1978 · TCP + IP</text><text x="421" y="83" text-anchor="middle" class="s1">Se separan: IP encamina,</text><text x="421" y="96" text-anchor="middle" class="s1">TCP da fiabilidad</text>
  <rect x="506" y="50" width="154" height="58" rx="5" fill="#d13c3c"/><text x="583" y="68" text-anchor="middle" class="t1">1-1-1983 · FLAG DAY</text><text x="583" y="83" text-anchor="middle" class="s1">ARPANET abandona NCP</text><text x="583" y="96" text-anchor="middle" class="s1">y adopta TCP/IP</text>
  <text x="20" y="130" class="k1">ETAPA 2 · LA WEB Y LA APERTURA COMERCIAL</text>
  <rect x="20" y="138" width="154" height="58" rx="5" fill="#2d8659"/><text x="97" y="156" text-anchor="middle" class="t1">1983-1987 · DNS</text><text x="97" y="171" text-anchor="middle" class="s1">Mockapetris. Sustituye al</text><text x="97" y="184" text-anchor="middle" class="s1">fichero HOSTS.TXT</text>
  <rect x="182" y="138" width="154" height="58" rx="5" fill="#2d8659"/><text x="259" y="156" text-anchor="middle" class="t1">1989-1991 · WWW</text><text x="259" y="171" text-anchor="middle" class="s1">Berners-Lee en el CERN:</text><text x="259" y="184" text-anchor="middle" class="s1">HTML + URL + HTTP</text>
  <rect x="344" y="138" width="154" height="58" rx="5" fill="#2d8659"/><text x="421" y="156" text-anchor="middle" class="t1">30-4-1993 · LIBRE</text><text x="421" y="171" text-anchor="middle" class="s1">El CERN cede la Web al</text><text x="421" y="184" text-anchor="middle" class="s1">dominio público. Mosaic</text>
  <rect x="506" y="138" width="154" height="58" rx="5" fill="#2d8659"/><text x="583" y="156" text-anchor="middle" class="t1">1990-1995</text><text x="583" y="171" text-anchor="middle" class="s1">Fin de ARPANET (1990) y</text><text x="583" y="184" text-anchor="middle" class="s1">privatización de NSFNET</text>
  <text x="20" y="218" class="k1">ETAPA 3 · MADUREZ, ESCALA Y CIFRADO</text>
  <rect x="20" y="226" width="154" height="58" rx="5" fill="#e89822"/><text x="97" y="244" text-anchor="middle" class="t1">2011-2019</text><text x="97" y="259" text-anchor="middle" class="s1">Agotamiento de IPv4:</text><text x="97" y="272" text-anchor="middle" class="s1">IANA 2011, RIPE 2019</text>
  <rect x="182" y="226" width="154" height="58" rx="5" fill="#e89822"/><text x="259" y="244" text-anchor="middle" class="t1">2015-2022</text><text x="259" y="259" text-anchor="middle" class="s1">HTTP/2 y HTTP/3. La Web</text><text x="259" y="272" text-anchor="middle" class="s1">pasa a ser binaria</text>
  <rect x="344" y="226" width="154" height="58" rx="5" fill="#e89822"/><text x="421" y="244" text-anchor="middle" class="t1">2018-2026 · TLS 1.3</text><text x="421" y="259" text-anchor="middle" class="s1">RFC 8446, reeditado en</text><text x="421" y="272" text-anchor="middle" class="s1">julio de 2026: RFC 9846</text>
  <rect x="506" y="226" width="154" height="58" rx="5" fill="#e89822"/><text x="583" y="244" text-anchor="middle" class="t1">28-3-2026 · IPv6</text><text x="583" y="259" text-anchor="middle" class="s1">Supera el 50% de accesos</text><text x="583" y="272" text-anchor="middle" class="s1">medidos por Google</text>
  <rect x="20" y="298" width="640" height="34" rx="5" fill="none" stroke="#0055a0" stroke-width="1.5"/>
  <text x="340" y="313" text-anchor="middle" class="k1">INTERNET (1983) es la infraestructura · LA WEB (1991) es UN SERVICIO que se ejecuta sobre ella</text>
  <text x="340" y="326" text-anchor="middle" class="n1">Sobre la misma infraestructura corren también el correo, el DNS, la transferencia de archivos y el acceso remoto</text>
  <text x="670" y="348" text-anchor="end" class="n1">[Fuente: elaboración propia sobre RFC 1, RFC 801, W3C y CERN]</text>
</svg>
```

---

## D2 · Quién gobierna qué en Internet

**Sección**: §1.2.1 — Organismos internacionales de regulación
**Propósito**: Separar los tres bloques de competencias —identificadores, estándares y otros ámbitos— para responder la pregunta típica de «qué organismo hace qué», e incorporar la transición IANA de 2016.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 372" role="img" aria-label="Mapa de la gobernanza de Internet en tres bloques: identificadores únicos gestionados por ICANN, la función IANA operada por PTI desde 2016 y los cinco registros regionales; estándares elaborados por el IETF bajo supervisión del IAB y el IESG dentro de la Internet Society; y otros ámbitos como el W3C para la Web, el IEEE para las capas físicas, la ITU-T y el foro de gobernanza de Internet, que no adopta decisiones vinculantes">
  <style>.t2{font:700 10.5px system-ui,sans-serif;fill:#fff}.s2{font:8.5px system-ui,sans-serif;fill:#fff}.d2{font:9px system-ui,sans-serif;fill:#333}.h2{font:700 13px system-ui,sans-serif;fill:#0055a0}.k2{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n2{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h2">Nadie manda en Internet: se coordina lo imprescindible</text>
  <text x="20" y="42" class="k2">IDENTIFICADORES ÚNICOS</text>
  <text x="237" y="42" class="k2">ESTÁNDARES TÉCNICOS</text>
  <text x="454" y="42" class="k2">OTROS ÁMBITOS</text>
  <rect x="20" y="50" width="206" height="46" rx="5" fill="#0055a0"/><text x="123" y="68" text-anchor="middle" class="t2">ICANN (1998)</text><text x="123" y="84" text-anchor="middle" class="s2">Coordina nombres y números</text>
  <rect x="237" y="50" width="206" height="46" rx="5" fill="#2d8659"/><text x="340" y="68" text-anchor="middle" class="t2">ISOC</text><text x="340" y="84" text-anchor="middle" class="s2">Paraguas institucional del IETF</text>
  <rect x="454" y="50" width="206" height="46" rx="5" fill="#e89822"/><text x="557" y="68" text-anchor="middle" class="t2">W3C (1994)</text><text x="557" y="84" text-anchor="middle" class="s2">Estándares de la WEB: HTML, CSS</text>
  <rect x="20" y="102" width="206" height="46" rx="5" fill="#0055a0"/><text x="123" y="120" text-anchor="middle" class="t2">Función IANA · PTI</text><text x="123" y="136" text-anchor="middle" class="s2">Raíz DNS, bloques IP, parámetros</text>
  <rect x="237" y="102" width="206" height="46" rx="5" fill="#2d8659"/><text x="340" y="120" text-anchor="middle" class="t2">IAB + IESG</text><text x="340" y="136" text-anchor="middle" class="s2">Arquitectura y aprobación</text>
  <rect x="454" y="102" width="206" height="46" rx="5" fill="#e89822"/><text x="557" y="120" text-anchor="middle" class="t2">IEEE</text><text x="557" y="136" text-anchor="middle" class="s2">802.3 Ethernet y 802.11 Wi-Fi</text>
  <rect x="20" y="154" width="206" height="46" rx="5" fill="#0055a0"/><text x="123" y="172" text-anchor="middle" class="t2">5 RIR</text><text x="123" y="188" text-anchor="middle" class="s2">ARIN · RIPE NCC · APNIC · LACNIC · AFRINIC</text>
  <rect x="237" y="154" width="206" height="46" rx="5" fill="#2d8659"/><text x="340" y="172" text-anchor="middle" class="t2">IETF</text><text x="340" y="188" text-anchor="middle" class="s2">Escribe los RFC. IRTF: investigación</text>
  <rect x="454" y="154" width="206" height="46" rx="5" fill="#888"/><text x="557" y="172" text-anchor="middle" class="t2">ITU-T · IGF</text><text x="557" y="188" text-anchor="middle" class="s2">El IGF dialoga: NO decide</text>
  <rect x="20" y="206" width="206" height="42" rx="5" fill="#eef3f8"/><text x="123" y="222" text-anchor="middle" class="d2">LIR (operadores)</text><text x="123" y="236" text-anchor="middle" class="n2">España pertenece a RIPE NCC</text>
  <rect x="237" y="206" width="423" height="42" rx="5" fill="#fdf3e3"/><text x="448" y="222" text-anchor="middle" class="d2">HTTP, TLS, IP, DNS y el correo son estándares del IETF, no del W3C</text><text x="448" y="236" text-anchor="middle" class="n2">El W3C estandariza lo que se ejecuta DENTRO del navegador; el IETF, cómo viaja por la red</text>
  <rect x="20" y="258" width="640" height="44" rx="5" fill="#fbeaea"/>
  <text x="340" y="276" text-anchor="middle" class="d2">TRANSICIÓN IANA: el contrato con el Gobierno de EE. UU. expiró el 30-9-2016</text>
  <text x="340" y="292" text-anchor="middle" class="n2">Desde el 1-10-2016 las funciones IANA las ejerce PTI, filial de ICANN, bajo modelo de múltiples partes interesadas</text>
  <rect x="20" y="312" width="640" height="34" rx="5" fill="none" stroke="#0055a0" stroke-width="1.5"/>
  <text x="340" y="327" text-anchor="middle" class="k2">ICANN reparte IDENTIFICADORES · IETF escribe PROTOCOLOS · W3C estandariza la WEB</text>
  <text x="340" y="340" text-anchor="middle" class="n2">Cadena de direcciones: IANA da bloques al RIR, el RIR al LIR (operador) y el LIR al usuario final</text>
  <text x="670" y="364" text-anchor="end" class="n2">[Fuente: ICANN, IETF, W3C, RIPE NCC]</text>
</svg>
```

---

## D3 · El camino de un estándar: del Internet-Draft al STD

**Sección**: §1.2.2 — Proceso de estandarización técnica y documentos RFC
**Propósito**: Mostrar el recorrido de un documento del IETF y, sobre todo, fijar las dos reglas que se preguntan: el borrador caduca a los seis meses y el RFC publicado es inmutable.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 356" role="img" aria-label="Camino de un estándar del IETF: un Internet-Draft que caduca a los seis meses es adoptado por un grupo de trabajo, pasa la última llamada y la aprobación del IESG y se publica como RFC con número inmutable; categorías de RFC: Standards Track con los escalones Proposed Standard e Internet Standard con número STD, Best Current Practice, Informational, Experimental e Historic">
  <style>.t3{font:700 10.5px system-ui,sans-serif;fill:#fff}.s3{font:8.5px system-ui,sans-serif;fill:#fff}.d3{font:9px system-ui,sans-serif;fill:#333}.h3{font:700 13px system-ui,sans-serif;fill:#0055a0}.k3{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n3{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h3">Un RFC publicado no se corrige nunca: se obsoleta o se actualiza</text>
  <text x="20" y="42" class="k3">EL RECORRIDO</text>
  <rect x="20" y="50" width="148" height="52" rx="5" fill="#888"/><text x="94" y="70" text-anchor="middle" class="t3">INTERNET-DRAFT</text><text x="94" y="86" text-anchor="middle" class="s3">Caduca a los 6 MESES</text>
  <rect x="184" y="50" width="148" height="52" rx="5" fill="#0055a0"/><text x="258" y="70" text-anchor="middle" class="t3">GRUPO DE TRABAJO</text><text x="258" y="86" text-anchor="middle" class="s3">Debate público y consenso</text>
  <rect x="348" y="50" width="148" height="52" rx="5" fill="#0055a0"/><text x="422" y="70" text-anchor="middle" class="t3">LAST CALL + IESG</text><text x="422" y="86" text-anchor="middle" class="s3">Última llamada y aprobación</text>
  <rect x="512" y="50" width="148" height="52" rx="5" fill="#2d8659"/><text x="586" y="70" text-anchor="middle" class="t3">RFC PUBLICADO</text><text x="586" y="86" text-anchor="middle" class="s3">Número definitivo e inmutable</text>
  <path d="M168 76 L180 76" stroke="#666" stroke-width="1.5" marker-end="url(#a3)"/>
  <path d="M332 76 L344 76" stroke="#666" stroke-width="1.5" marker-end="url(#a3)"/>
  <path d="M496 76 L508 76" stroke="#666" stroke-width="1.5" marker-end="url(#a3)"/>
  <defs><marker id="a3" markerWidth="7" markerHeight="7" refX="6" refY="3" orient="auto"><path d="M0,0 L6,3 L0,6 z" fill="#666"/></marker></defs>
  <rect x="20" y="112" width="640" height="24" rx="4" fill="#fbeaea"/>
  <text x="340" y="128" text-anchor="middle" class="d3">Un Internet-Draft NO es un estándar y NO puede citarse como referencia normativa</text>
  <text x="20" y="158" class="k3">CATEGORÍAS DE RFC · no todo RFC es un estándar</text>
  <rect x="20" y="166" width="312" height="40" rx="4" fill="#0055a0"/><text x="176" y="182" text-anchor="middle" class="t3">STANDARDS TRACK</text><text x="176" y="197" text-anchor="middle" class="s3">Proposed Standard → Internet Standard (serie STD)</text>
  <rect x="348" y="166" width="312" height="40" rx="4" fill="#2d8659"/><text x="504" y="182" text-anchor="middle" class="t3">BEST CURRENT PRACTICE</text><text x="504" y="197" text-anchor="middle" class="s3">Prácticas y procedimientos. Se numera como BCP n</text>
  <rect x="20" y="212" width="204" height="38" rx="4" fill="#eef3f8"/><text x="122" y="228" text-anchor="middle" class="d3">INFORMATIONAL</text><text x="122" y="242" text-anchor="middle" class="n3">Sin pretensión normativa</text>
  <rect x="238" y="212" width="204" height="38" rx="4" fill="#fdf3e3"/><text x="340" y="228" text-anchor="middle" class="d3">EXPERIMENTAL</text><text x="340" y="242" text-anchor="middle" class="n3">Especificación en pruebas</text>
  <rect x="456" y="212" width="204" height="38" rx="4" fill="#fbeaea"/><text x="558" y="228" text-anchor="middle" class="d3">HISTORIC</text><text x="558" y="242" text-anchor="middle" class="n3">Superado y desaconsejado</text>
  <rect x="20" y="260" width="640" height="38" rx="4" fill="#fdf3e3"/>
  <text x="340" y="276" text-anchor="middle" class="d3">EJEMPLOS VERIFICADOS: STD 97 = RFC 9110 (HTTP) · STD 99 = RFC 9112 (HTTP/1.1) · STD 86 = RFC 8200 (IPv6)</text>
  <text x="340" y="290" text-anchor="middle" class="n3">STD 102 = RFC 9915 (DHCPv6, enero de 2026) · BCP 5 = RFC 1918 (direccionamiento privado)</text>
  <rect x="20" y="308" width="640" height="26" rx="4" fill="none" stroke="#d13c3c" stroke-width="1.5"/>
  <text x="340" y="325" text-anchor="middle" class="k3">El número STD no cambia aunque se reedite el RFC que lo desarrolla</text>
  <text x="670" y="348" text-anchor="end" class="n3">[Fuente: RFC Editor; RFC 2026 y RFC 6410]</text>
</svg>
```

---
## D4 · Pila TCP/IP frente al modelo OSI

**Sección**: §2.1.1 — Pila TCP/IP y correspondencia con el modelo OSI
**Propósito**: Fijar la correspondencia exacta entre las siete capas de OSI y las cuatro de TCP/IP, con los protocolos y la PDU de cada nivel. Es la tabla de la que salen más preguntas del bloque de arquitectura.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 372" role="img" aria-label="Comparación entre el modelo OSI de siete capas y el modelo TCP/IP de cuatro capas: aplicación, presentación y sesión de OSI se corresponden con la capa de aplicación de TCP/IP; transporte y red se corresponden una a una; enlace de datos y física se corresponden con la capa de acceso a red. Se indican los protocolos y la unidad de datos de cada nivel: mensaje, segmento o datagrama, paquete y trama">
  <style>.t4{font:700 10px system-ui,sans-serif;fill:#fff}.s4{font:8.5px system-ui,sans-serif;fill:#fff}.d4{font:9px system-ui,sans-serif;fill:#333}.h4{font:700 13px system-ui,sans-serif;fill:#0055a0}.k4{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n4{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h4">OSI es el modelo de referencia; TCP/IP es la pila que funciona</text>
  <text x="20" y="42" class="k4">MODELO OSI · 7 CAPAS</text>
  <text x="214" y="42" class="k4">TCP/IP · 4 CAPAS</text>
  <text x="406" y="42" class="k4">PROTOCOLOS Y UNIDAD DE DATOS (PDU)</text>
  <rect x="20" y="50" width="180" height="34" rx="4" fill="#eef3f8"/><text x="110" y="71" text-anchor="middle" class="d4">7 · Aplicación</text>
  <rect x="20" y="86" width="180" height="34" rx="4" fill="#eef3f8"/><text x="110" y="107" text-anchor="middle" class="d4">6 · Presentación</text>
  <rect x="20" y="122" width="180" height="34" rx="4" fill="#eef3f8"/><text x="110" y="143" text-anchor="middle" class="d4">5 · Sesión</text>
  <rect x="20" y="158" width="180" height="34" rx="4" fill="#eef3f8"/><text x="110" y="179" text-anchor="middle" class="d4">4 · Transporte</text>
  <rect x="20" y="194" width="180" height="34" rx="4" fill="#eef3f8"/><text x="110" y="215" text-anchor="middle" class="d4">3 · Red</text>
  <rect x="20" y="230" width="180" height="34" rx="4" fill="#eef3f8"/><text x="110" y="251" text-anchor="middle" class="d4">2 · Enlace de datos</text>
  <rect x="20" y="266" width="180" height="34" rx="4" fill="#eef3f8"/><text x="110" y="287" text-anchor="middle" class="d4">1 · Física</text>
  <rect x="214" y="50" width="178" height="106" rx="4" fill="#0055a0"/><text x="303" y="96" text-anchor="middle" class="t4">APLICACIÓN</text><text x="303" y="112" text-anchor="middle" class="s4">Absorbe TRES capas de OSI</text>
  <rect x="214" y="158" width="178" height="34" rx="4" fill="#2d8659"/><text x="303" y="179" text-anchor="middle" class="t4">TRANSPORTE</text>
  <rect x="214" y="194" width="178" height="34" rx="4" fill="#e89822"/><text x="303" y="215" text-anchor="middle" class="t4">INTERNET</text>
  <rect x="214" y="230" width="178" height="70" rx="4" fill="#7a2f8a"/><text x="303" y="260" text-anchor="middle" class="t4">ACCESO A RED</text><text x="303" y="276" text-anchor="middle" class="s4">Absorbe DOS capas de OSI</text>
  <rect x="406" y="50" width="254" height="106" rx="4" fill="#fdf3e3"/><text x="533" y="76" text-anchor="middle" class="d4">HTTP · HTTPS · DNS · SMTP · IMAP</text><text x="533" y="92" text-anchor="middle" class="d4">FTP · SSH · DHCP · NTP · SNMP</text><text x="533" y="112" text-anchor="middle" class="n4">PDU: MENSAJE (datos de aplicación)</text><text x="533" y="130" text-anchor="middle" class="n4">Dispositivo: pasarela y proxy</text>
  <rect x="406" y="158" width="254" height="34" rx="4" fill="#eaf5ef"/><text x="533" y="173" text-anchor="middle" class="d4">TCP · UDP · QUIC (sobre UDP)</text><text x="533" y="186" text-anchor="middle" class="n4">PDU: SEGMENTO (TCP) o DATAGRAMA (UDP)</text>
  <rect x="406" y="194" width="254" height="34" rx="4" fill="#fdf3e3"/><text x="533" y="209" text-anchor="middle" class="d4">IPv4 · IPv6 · ICMP · IGMP · BGP · OSPF</text><text x="533" y="222" text-anchor="middle" class="n4">PDU: PAQUETE · Dispositivo: encaminador</text>
  <rect x="406" y="230" width="254" height="70" rx="4" fill="#f3ecf6"/><text x="533" y="252" text-anchor="middle" class="d4">Ethernet 802.3 · Wi-Fi 802.11 · PPP</text><text x="533" y="268" text-anchor="middle" class="n4">PDU: TRAMA (enlace) y BIT (física)</text><text x="533" y="286" text-anchor="middle" class="n4">Dispositivo: conmutador y concentrador</text>
  <rect x="20" y="308" width="640" height="34" rx="5" fill="none" stroke="#0055a0" stroke-width="1.5"/>
  <text x="340" y="323" text-anchor="middle" class="k4">EL RELOJ DE ARENA: muchas tecnologías de acceso abajo, muchas aplicaciones arriba y UN SOLO protocolo en el centro, IP</text>
  <text x="340" y="336" text-anchor="middle" class="n4">ARP queda entre las capas 2 y 3: el RFC 1122 lo sitúa en la de enlace · La variante didáctica de 5 capas separa física y enlace</text>
  <text x="670" y="364" text-anchor="end" class="n4">[Fuente: RFC 1122; ISO/IEC 7498-1]</text>
</svg>
```

---

## D5 · Encapsulamiento y desencapsulamiento

**Sección**: §2.1.2 — Encapsulamiento y transmisión de datos
**Propósito**: Ver cómo cada capa antepone su cabecera y por qué el nombre de la PDU cambia en cada nivel, junto con el concepto de MTU y lo que se modifica en cada salto.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 352" role="img" aria-label="Proceso de encapsulamiento: el mensaje HTTP de la capa de aplicación recibe la cabecera TCP y pasa a llamarse segmento, después la cabecera IP y pasa a llamarse paquete, después la cabecera Ethernet y la secuencia de comprobación y pasa a llamarse trama, y finalmente se transmite como bits. Se indica que la MTU de Ethernet es de 1500 bytes y que las direcciones MAC cambian en cada salto mientras las direcciones IP se conservan de extremo a extremo">
  <style>.t5{font:700 9.5px system-ui,sans-serif;fill:#fff}.s5{font:8.5px system-ui,sans-serif;fill:#fff}.d5{font:9px system-ui,sans-serif;fill:#333}.h5{font:700 13px system-ui,sans-serif;fill:#0055a0}.k5{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n5{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h5">Cada capa trata como datos opacos todo lo que le entrega la superior</text>
  <text x="20" y="42" class="k5">BAJADA POR LA PILA EN EL EMISOR · el receptor hace el recorrido inverso</text>
  <rect x="20" y="50" width="118" height="36" rx="4" fill="#0055a0"/><text x="79" y="66" text-anchor="middle" class="t5">APLICACIÓN</text><text x="79" y="79" text-anchor="middle" class="s5">PDU: mensaje</text>
  <rect x="146" y="50" width="514" height="36" rx="4" fill="#eef3f8"/><text x="403" y="72" text-anchor="middle" class="d5">GET /tramites HTTP/1.1 · Host: sede.madrid.es · Cookie: ...</text>
  <rect x="20" y="92" width="118" height="36" rx="4" fill="#2d8659"/><text x="79" y="108" text-anchor="middle" class="t5">TRANSPORTE</text><text x="79" y="121" text-anchor="middle" class="s5">PDU: segmento</text>
  <rect x="146" y="92" width="128" height="36" rx="4" fill="#2d8659"/><text x="210" y="108" text-anchor="middle" class="t5">Cabecera TCP</text><text x="210" y="121" text-anchor="middle" class="s5">20 B · puerto 443</text>
  <rect x="282" y="92" width="378" height="36" rx="4" fill="#eef3f8"/><text x="471" y="114" text-anchor="middle" class="d5">Mensaje HTTP</text>
  <rect x="20" y="134" width="118" height="36" rx="4" fill="#e89822"/><text x="79" y="150" text-anchor="middle" class="t5">INTERNET</text><text x="79" y="163" text-anchor="middle" class="s5">PDU: paquete</text>
  <rect x="146" y="134" width="128" height="36" rx="4" fill="#e89822"/><text x="210" y="150" text-anchor="middle" class="t5">Cabecera IP</text><text x="210" y="163" text-anchor="middle" class="s5">IP origen y destino</text>
  <rect x="282" y="134" width="128" height="36" rx="4" fill="#2d8659"/><text x="346" y="156" text-anchor="middle" class="t5">Cabecera TCP</text>
  <rect x="418" y="134" width="242" height="36" rx="4" fill="#eef3f8"/><text x="539" y="156" text-anchor="middle" class="d5">Mensaje HTTP</text>
  <rect x="20" y="176" width="118" height="36" rx="4" fill="#7a2f8a"/><text x="79" y="192" text-anchor="middle" class="t5">ENLACE</text><text x="79" y="205" text-anchor="middle" class="s5">PDU: trama</text>
  <rect x="146" y="176" width="118" height="36" rx="4" fill="#7a2f8a"/><text x="205" y="192" text-anchor="middle" class="t5">Cabecera Ethernet</text><text x="205" y="205" text-anchor="middle" class="s5">MAC origen y destino</text>
  <rect x="272" y="176" width="110" height="36" rx="4" fill="#e89822"/><text x="327" y="198" text-anchor="middle" class="t5">Cabecera IP</text>
  <rect x="390" y="176" width="110" height="36" rx="4" fill="#2d8659"/><text x="445" y="198" text-anchor="middle" class="t5">Cabecera TCP</text>
  <rect x="508" y="176" width="90" height="36" rx="4" fill="#eef3f8"/><text x="553" y="198" text-anchor="middle" class="d5">Mensaje</text>
  <rect x="606" y="176" width="54" height="36" rx="4" fill="#d13c3c"/><text x="633" y="198" text-anchor="middle" class="t5">FCS</text>
  <rect x="20" y="218" width="118" height="30" rx="4" fill="#555"/><text x="79" y="237" text-anchor="middle" class="t5">FÍSICA · bits</text>
  <rect x="146" y="218" width="514" height="30" rx="4" fill="#f0f0f0"/><text x="403" y="237" text-anchor="middle" class="d5">1 0 1 1 0 0 1 0 · señales eléctricas, ópticas o radioeléctricas</text>
  <rect x="20" y="258" width="640" height="26" rx="4" fill="#fdf3e3"/>
  <text x="340" y="275" text-anchor="middle" class="d5">MTU de Ethernet: 1.500 bytes de carga útil · si el paquete no cabe, IPv4 permite fragmentar en el camino; IPv6, solo en el origen</text>
  <rect x="20" y="292" width="640" height="34" rx="5" fill="none" stroke="#0055a0" stroke-width="1.5"/>
  <text x="340" y="307" text-anchor="middle" class="k5">Las direcciones MAC CAMBIAN en cada salto · las direcciones IP se CONSERVAN de extremo a extremo</text>
  <text x="340" y="320" text-anchor="middle" class="n5">Salvo que haya un NAT, que precisamente lo que hace es reescribirlas · el TTL se decrementa en cada encaminador</text>
  <text x="670" y="344" text-anchor="end" class="n5">[Fuente: RFC 1122; RFC 791 y RFC 8200]</text>
</svg>
```

---

## D6 · Internet como red de redes: AS, tránsito, *peering* e IXP

**Sección**: §2.2.1 — Sistemas Autónomos y puntos de intercambio de tráfico
**Propósito**: Explicar por qué el encaminamiento entre operadores es una cuestión económica antes que técnica, y distinguir tránsito de *peering*, que es la pregunta segura del epígrafe.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 372" role="img" aria-label="Internet como red de redes: sistemas autónomos de tránsito de primer nivel que alcanzan toda la tabla global mediante acuerdos de peering, operadores de segundo nivel que compran tránsito, puntos neutros de intercambio como ESPANIX y DE-CIX Madrid donde las redes intercambian tráfico directamente, y el sistema autónomo del Ayuntamiento con su propio número y prefijo. Se compara el tránsito, que se paga y alcanza todo Internet, con el peering, que suele ser gratuito y solo alcanza las redes del otro y sus clientes">
  <style>.t6{font:700 10px system-ui,sans-serif;fill:#fff}.s6{font:8.5px system-ui,sans-serif;fill:#fff}.d6{font:9px system-ui,sans-serif;fill:#333}.h6{font:700 13px system-ui,sans-serif;fill:#0055a0}.k6{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n6{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h6">Entre operadores, encaminar es una decisión económica, no una métrica</text>
  <text x="20" y="42" class="k6">JERARQUÍA DE INTERCONEXIÓN</text>
  <rect x="20" y="50" width="640" height="42" rx="5" fill="#0055a0"/><text x="340" y="68" text-anchor="middle" class="t6">AS DE TRÁNSITO GLOBAL (Tier 1)</text><text x="340" y="84" text-anchor="middle" class="s6">Alcanzan la tabla global completa SOLO mediante acuerdos de peering: no pagan tránsito a nadie</text>
  <path d="M200 92 L200 108" stroke="#666" stroke-width="1.5" marker-end="url(#a6)"/>
  <path d="M480 92 L480 108" stroke="#666" stroke-width="1.5" marker-end="url(#a6)"/>
  <defs><marker id="a6" markerWidth="7" markerHeight="7" refX="6" refY="3" orient="auto"><path d="M0,0 L6,3 L0,6 z" fill="#666"/></marker></defs>
  <rect x="20" y="112" width="312" height="42" rx="5" fill="#2d8659"/><text x="176" y="130" text-anchor="middle" class="t6">OPERADOR NACIONAL (Tier 2)</text><text x="176" y="146" text-anchor="middle" class="s6">Compra tránsito y además hace peering</text>
  <rect x="348" y="112" width="312" height="42" rx="5" fill="#2d8659"/><text x="504" y="130" text-anchor="middle" class="t6">PROVEEDOR DE CONTENIDO O CDN</text><text x="504" y="146" text-anchor="middle" class="s6">Le interesa acercar el contenido al usuario</text>
  <path d="M176 154 L176 170" stroke="#666" stroke-width="1.5" marker-end="url(#a6)"/>
  <path d="M504 154 L504 170" stroke="#666" stroke-width="1.5" marker-end="url(#a6)"/>
  <rect x="20" y="174" width="640" height="46" rx="5" fill="#e89822"/><text x="340" y="192" text-anchor="middle" class="t6">PUNTO NEUTRO · IXP</text><text x="340" y="207" text-anchor="middle" class="s6">ESPANIX (13-5-1997, picos superiores a 2 Tbps) y DE-CIX Madrid (2016, más de 1,5 Tbit/s)</text>
  <path d="M176 220 L176 236" stroke="#666" stroke-width="1.5" marker-end="url(#a6)"/>
  <rect x="20" y="240" width="312" height="42" rx="5" fill="#7a2f8a"/><text x="176" y="258" text-anchor="middle" class="t6">AS DEL AYUNTAMIENTO</text><text x="176" y="274" text-anchor="middle" class="s6">ASN de 32 bits y prefijo propio anunciado por BGP</text>
  <rect x="348" y="240" width="312" height="42" rx="5" fill="#eef3f8"/><text x="504" y="256" text-anchor="middle" class="d6">≈ 80.000 AS activos en 2026</text><text x="504" y="270" text-anchor="middle" class="n6">Más de 1.000.000 de prefijos IPv4 y ≈ 250.000 de IPv6</text><text x="504" y="280" text-anchor="middle" class="n6">Dentro del AS se usan IGP: OSPF, IS-IS, RIP</text>
  <rect x="20" y="290" width="312" height="42" rx="5" fill="#fbeaea"/><text x="176" y="308" text-anchor="middle" class="d6">TRÁNSITO · se PAGA</text><text x="176" y="324" text-anchor="middle" class="n6">Da acceso a TODO Internet</text>
  <rect x="348" y="290" width="312" height="42" rx="5" fill="#eaf5ef"/><text x="504" y="308" text-anchor="middle" class="d6">PEERING · normalmente GRATUITO</text><text x="504" y="324" text-anchor="middle" class="n6">Solo alcanza al otro AS y a SUS clientes</text>
  <text x="340" y="348" text-anchor="middle" class="k6">BGP-4 (RFC 4271, TCP/179) es el ÚNICO protocolo de encaminamiento exterior de Internet</text>
  <text x="670" y="364" text-anchor="end" class="n6">[Fuente: RFC 4271; CIDR Report; ESPANIX y DE-CIX]</text>
</svg>
```

---
## D7 · Agotamiento de IPv4 y mecanismos de coexistencia con IPv6

**Sección**: §2.2.2 — Coexistencia de los protocolos IPv4 e IPv6
**Propósito**: Encadenar las tres fechas del agotamiento, los paliativos que solo lo aplazaron y los tres —y solo tres— mecanismos de coexistencia posibles.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 372" role="img" aria-label="Agotamiento de IPv4 y coexistencia con IPv6: la IANA agotó su reserva el 3 de febrero de 2011, RIPE NCC entró en la fase del último bloque barra ocho el 14 de septiembre de 2012 y alcanzó el agotamiento pleno el 25 de noviembre de 2019. Paliativos: CIDR, direccionamiento privado, NAT y CGNAT. Comparación entre IPv4 de 32 bits e IPv6 de 128 bits con cabecera fija de 40 bytes y sin difusión. Los tres mecanismos de coexistencia son la doble pila, los túneles y la traducción con NAT64 y DNS64">
  <style>.t7{font:700 10px system-ui,sans-serif;fill:#fff}.s7{font:8.5px system-ui,sans-serif;fill:#fff}.d7{font:9px system-ui,sans-serif;fill:#333}.h7{font:700 13px system-ui,sans-serif;fill:#0055a0}.k7{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n7{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h7">IPv4 e IPv6 son incompatibles: por eso hacen falta mecanismos de coexistencia</text>
  <text x="20" y="42" class="k7">CRONOLOGÍA DEL AGOTAMIENTO</text>
  <rect x="20" y="50" width="206" height="46" rx="5" fill="#d13c3c"/><text x="123" y="68" text-anchor="middle" class="t7">3-2-2011 · IANA</text><text x="123" y="84" text-anchor="middle" class="s7">Entrega sus últimos cinco /8</text>
  <rect x="237" y="50" width="206" height="46" rx="5" fill="#d13c3c"/><text x="340" y="68" text-anchor="middle" class="t7">14-9-2012 · RIPE NCC</text><text x="340" y="84" text-anchor="middle" class="s7">Último /8: un solo /22 por operador</text>
  <rect x="454" y="50" width="206" height="46" rx="5" fill="#d13c3c"/><text x="557" y="68" text-anchor="middle" class="t7">25-11-2019 · RIPE NCC</text><text x="557" y="84" text-anchor="middle" class="s7">Agotado: solo lista de espera</text>
  <text x="20" y="118" class="k7">PALIATIVOS QUE APLAZARON EL PROBLEMA, PERO NO CREAN DIRECCIONES</text>
  <rect x="20" y="126" width="154" height="42" rx="4" fill="#eef3f8"/><text x="97" y="142" text-anchor="middle" class="d7">CIDR</text><text x="97" y="157" text-anchor="middle" class="n7">Sin clases; prefijo variable</text>
  <rect x="182" y="126" width="154" height="42" rx="4" fill="#eef3f8"/><text x="259" y="142" text-anchor="middle" class="d7">RFC 1918 · privadas</text><text x="259" y="157" text-anchor="middle" class="n7">10/8 · 172.16/12 · 192.168/16</text>
  <rect x="344" y="126" width="154" height="42" rx="4" fill="#eef3f8"/><text x="421" y="142" text-anchor="middle" class="d7">NAT y PAT</text><text x="421" y="157" text-anchor="middle" class="n7">Rompe el extremo a extremo</text>
  <rect x="506" y="126" width="154" height="42" rx="4" fill="#fbeaea"/><text x="583" y="142" text-anchor="middle" class="d7">CGNAT · RFC 6598</text><text x="583" y="157" text-anchor="middle" class="n7">100.64.0.0/10 · sin trazabilidad</text>
  <text x="20" y="190" class="k7">LOS DOS PROTOCOLOS</text>
  <rect x="20" y="198" width="312" height="58" rx="5" fill="#888"/><text x="176" y="216" text-anchor="middle" class="t7">IPv4 · 32 bits</text><text x="176" y="231" text-anchor="middle" class="s7">≈ 4.294 millones · cabecera de 20 a 60 bytes</text><text x="176" y="246" text-anchor="middle" class="s7">Con suma de control, difusión y ARP</text>
  <rect x="348" y="198" width="312" height="58" rx="5" fill="#0055a0"/><text x="504" y="216" text-anchor="middle" class="t7">IPv6 · 128 bits · RFC 8200</text><text x="504" y="231" text-anchor="middle" class="s7">Cabecera FIJA de 40 bytes, sin suma de control</text><text x="504" y="246" text-anchor="middle" class="s7">Sin difusión: multidifusión y anycast · subred /64</text>
  <text x="20" y="278" class="k7">LOS TRES MECANISMOS DE COEXISTENCIA · no hay ningún otro</text>
  <rect x="20" y="286" width="206" height="46" rx="5" fill="#2d8659"/><text x="123" y="304" text-anchor="middle" class="t7">DOBLE PILA</text><text x="123" y="320" text-anchor="middle" class="s7">Ambas pilas a la vez · RECOMENDADO</text>
  <rect x="237" y="286" width="206" height="46" rx="5" fill="#e89822"/><text x="340" y="304" text-anchor="middle" class="t7">TÚNELES</text><text x="340" y="320" text-anchor="middle" class="s7">6in4, 6to4, Teredo, GRE, 6rd</text>
  <rect x="454" y="286" width="206" height="46" rx="5" fill="#e89822"/><text x="557" y="304" text-anchor="middle" class="t7">TRADUCCIÓN</text><text x="557" y="320" text-anchor="middle" class="s7">NAT64 + DNS64 · 464XLAT</text>
  <text x="340" y="348" text-anchor="middle" class="k7">España está en torno al 10 % de adopción de IPv6, muy por debajo de la media mundial, que superó el 50 % el 28-3-2026</text>
  <text x="670" y="364" text-anchor="end" class="n7">[Fuente: RFC 8200, RFC 1918, RFC 6598; RIPE NCC; Google IPv6]</text>
</svg>
```

---

## D8 · DNS: jerarquía y resolución de un nombre paso a paso

**Sección**: §2.2.3 — Sistema de Nombres de Dominio
**Propósito**: Distinguir consulta recursiva de iterativa —el error más frecuente del epígrafe— y ver de dónde sale cada respuesta parcial hasta llegar al registro A.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 372" role="img" aria-label="Jerarquía del DNS desde la raíz con trece identidades de servidor hasta el dominio de tercer nivel, y resolución paso a paso de sede punto madrid punto es: el cliente lanza una consulta recursiva al resolutor y este realiza consultas iterativas a la raíz, al servidor del dominio es y al servidor autoritativo de madrid punto es, cachea la respuesta durante su tiempo de vida y la entrega al cliente. El DNS usa el puerto 53, UDP para consultas y TCP para respuestas grandes y transferencias de zona">
  <style>.t8{font:700 10px system-ui,sans-serif;fill:#fff}.s8{font:8.5px system-ui,sans-serif;fill:#fff}.d8{font:9px system-ui,sans-serif;fill:#333}.h8{font:700 13px system-ui,sans-serif;fill:#0055a0}.k8{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n8{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h8">El cliente pregunta una vez; el resolutor pregunta tres</text>
  <text x="20" y="42" class="k8">LA JERARQUÍA · un nombre se lee de derecha a izquierda</text>
  <rect x="20" y="50" width="154" height="46" rx="5" fill="#0055a0"/><text x="97" y="68" text-anchor="middle" class="t8">RAÍZ · el punto final</text><text x="97" y="84" text-anchor="middle" class="s8">13 identidades, A a M</text>
  <rect x="182" y="50" width="154" height="46" rx="5" fill="#0055a0"/><text x="259" y="68" text-anchor="middle" class="t8">TLD · es</text><text x="259" y="84" text-anchor="middle" class="s8">ccTLD gestionado por Red.es</text>
  <rect x="344" y="50" width="154" height="46" rx="5" fill="#2d8659"/><text x="421" y="68" text-anchor="middle" class="t8">2.º NIVEL · madrid.es</text><text x="421" y="84" text-anchor="middle" class="s8">Zona del Ayuntamiento</text>
  <rect x="506" y="50" width="154" height="46" rx="5" fill="#2d8659"/><text x="583" y="68" text-anchor="middle" class="t8">SUBDOMINIO · sede</text><text x="583" y="84" text-anchor="middle" class="s8">sede.madrid.es</text>
  <text x="20" y="118" class="k8">RESOLUCIÓN DE sede.madrid.es</text>
  <rect x="20" y="126" width="640" height="28" rx="4" fill="#fdf3e3"/><circle cx="38" cy="140" r="9" fill="#e89822"/><text x="38" y="143" text-anchor="middle" class="t8">1</text><text x="56" y="144" class="d8">CLIENTE → RESOLUTOR: consulta RECURSIVA. «Dame la dirección de sede.madrid.es, resuélvelo tú»</text>
  <rect x="20" y="158" width="640" height="28" rx="4" fill="#eef3f8"/><circle cx="38" cy="172" r="9" fill="#0055a0"/><text x="38" y="175" text-anchor="middle" class="t8">2</text><text x="56" y="176" class="d8">RESOLUTOR → RAÍZ: consulta ITERATIVA. La raíz no lo sabe, pero responde con los NS de .es</text>
  <rect x="20" y="190" width="640" height="28" rx="4" fill="#eef3f8"/><circle cx="38" cy="204" r="9" fill="#0055a0"/><text x="38" y="207" text-anchor="middle" class="t8">3</text><text x="56" y="208" class="d8">RESOLUTOR → SERVIDOR DE .es: responde con los NS autoritativos de madrid.es</text>
  <rect x="20" y="222" width="640" height="28" rx="4" fill="#eef3f8"/><circle cx="38" cy="236" r="9" fill="#0055a0"/><text x="38" y="239" text-anchor="middle" class="t8">4</text><text x="56" y="240" class="d8">RESOLUTOR → AUTORITATIVO DE madrid.es: devuelve el registro A (IPv4) o AAAA (IPv6)</text>
  <rect x="20" y="254" width="640" height="28" rx="4" fill="#eaf5ef"/><circle cx="38" cy="268" r="9" fill="#2d8659"/><text x="38" y="271" text-anchor="middle" class="t8">5</text><text x="56" y="272" class="d8">RESOLUTOR: guarda la respuesta en caché durante su TTL y la entrega al cliente</text>
  <rect x="20" y="290" width="312" height="40" rx="4" fill="#fdf3e3"/><text x="176" y="306" text-anchor="middle" class="d8">PUERTO 53</text><text x="176" y="321" text-anchor="middle" class="n8">UDP para consultas · TCP si la respuesta es grande</text>
  <rect x="348" y="290" width="312" height="40" rx="4" fill="#fbeaea"/><text x="504" y="306" text-anchor="middle" class="d8">TRANSFERENCIA DE ZONA</text><text x="504" y="321" text-anchor="middle" class="n8">AXFR completa e IXFR incremental: SIEMPRE por TCP</text>
  <text x="340" y="348" text-anchor="middle" class="k8">Registros: A · AAAA · CNAME · MX · NS · PTR · SOA · TXT · SRV · CAA</text>
  <text x="670" y="364" text-anchor="end" class="n8">[Fuente: RFC 1034 y RFC 1035; ICANN]</text>
</svg>
```

---

## D9 · Seguridad del DNS: qué resuelve DNSSEC y qué resuelven DoT y DoH

**Sección**: §2.2.3 — Sistema de Nombres de Dominio
**Propósito**: Fijar que son **dos problemas distintos con dos soluciones distintas y complementarias**, que es exactamente lo que se pregunta con trampa.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 340" role="img" aria-label="Seguridad del DNS: el problema de la autenticidad, es decir el envenenamiento de caché y las respuestas falsas, lo resuelve DNSSEC firmando las respuestas; el problema de la confidencialidad, es decir que cualquiera puede ver qué sitios se consultan, lo resuelven DNS sobre TLS en el puerto 853 y DNS sobre HTTPS en el 443. DNSSEC no cifra y DoT y DoH no autentican la zona: son complementarios">
  <style>.t9{font:700 10px system-ui,sans-serif;fill:#fff}.s9{font:8.5px system-ui,sans-serif;fill:#fff}.d9{font:9px system-ui,sans-serif;fill:#333}.h9{font:700 13px system-ui,sans-serif;fill:#0055a0}.k9{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n9{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h9">DNSSEC autentica y no cifra; DoT y DoH cifran y no autentican la zona</text>
  <text x="20" y="42" class="k9">DOS PROBLEMAS DISTINTOS DEL DNS ORIGINAL</text>
  <rect x="20" y="50" width="312" height="44" rx="5" fill="#d13c3c"/><text x="176" y="68" text-anchor="middle" class="t9">PROBLEMA 1 · ¿ES VERDAD LA RESPUESTA?</text><text x="176" y="84" text-anchor="middle" class="s9">Envenenamiento de caché y respuestas suplantadas</text>
  <rect x="348" y="50" width="312" height="44" rx="5" fill="#d13c3c"/><text x="504" y="68" text-anchor="middle" class="t9">PROBLEMA 2 · ¿QUIÉN VE MIS CONSULTAS?</text><text x="504" y="84" text-anchor="middle" class="s9">El DNS clásico viaja en claro: revela qué se visita</text>
  <path d="M176 94 L176 110" stroke="#666" stroke-width="1.5" marker-end="url(#a9)"/>
  <path d="M504 94 L504 110" stroke="#666" stroke-width="1.5" marker-end="url(#a9)"/>
  <defs><marker id="a9" markerWidth="7" markerHeight="7" refX="6" refY="3" orient="auto"><path d="M0,0 L6,3 L0,6 z" fill="#666"/></marker></defs>
  <rect x="20" y="114" width="312" height="80" rx="5" fill="#2d8659"/><text x="176" y="134" text-anchor="middle" class="t9">DNSSEC · RFC 4033 a 4035</text><text x="176" y="150" text-anchor="middle" class="s9">FIRMA digitalmente los datos de la zona</text><text x="176" y="164" text-anchor="middle" class="s9">Cadena de confianza desde la raíz</text><text x="176" y="180" text-anchor="middle" class="s9">Aporta AUTENTICIDAD e INTEGRIDAD</text>
  <rect x="348" y="114" width="312" height="80" rx="5" fill="#0055a0"/><text x="504" y="134" text-anchor="middle" class="t9">DoT (TCP/853) y DoH (HTTPS/443)</text><text x="504" y="150" text-anchor="middle" class="s9">CIFRAN el transporte de la consulta</text><text x="504" y="164" text-anchor="middle" class="s9">RFC 7858 y RFC 8484</text><text x="504" y="180" text-anchor="middle" class="s9">Aportan CONFIDENCIALIDAD</text>
  <rect x="20" y="202" width="312" height="26" rx="4" fill="#fbeaea"/><text x="176" y="219" text-anchor="middle" class="n9">NO cifra: la respuesta sigue siendo legible</text>
  <rect x="348" y="202" width="312" height="26" rx="4" fill="#fbeaea"/><text x="504" y="219" text-anchor="middle" class="n9">NO garantizan que el dato de la zona sea auténtico</text>
  <rect x="20" y="238" width="640" height="26" rx="4" fill="#fdf3e3"/>
  <text x="340" y="255" text-anchor="middle" class="d9">A julio de 2026, 1.348 de los 1.437 dominios de primer nivel de la raíz estaban firmados con DNSSEC (≈ 93,8 %)</text>
  <rect x="20" y="274" width="640" height="34" rx="5" fill="none" stroke="#0055a0" stroke-width="1.5"/>
  <text x="340" y="289" text-anchor="middle" class="k9">SON COMPLEMENTARIOS, NO ALTERNATIVOS: lo ideal es DNSSEC en la zona propia y DoT o DoH en el cliente</text>
  <text x="340" y="302" text-anchor="middle" class="n9">Otras amenazas: secuestro del dominio en el registrador, dominios homógrafos y exfiltración por túnel DNS</text>
  <text x="670" y="332" text-anchor="end" class="n9">[Fuente: RFC 4033-4035, RFC 7858, RFC 8484; ICANN]</text>
</svg>
```

---
## D10 · Correo electrónico: agentes, protocolos, puertos y autenticación

**Sección**: §3.1.1 — Correo electrónico y sus protocolos
**Propósito**: Separar con claridad el protocolo de **envío** del de **recogida** —el error más penalizado del bloque— y añadir la tríada SPF, DKIM y DMARC con su reedición de 2026.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 372" role="img" aria-label="Recorrido de un mensaje de correo desde el cliente emisor al agente de envío en el puerto 587, de ahí al agente de transferencia del dominio destino por el puerto 25, y finalmente al buzón, del que el destinatario lo recoge con IMAP en el 993 o POP3 en el 995. Puertos de SMTP, POP3 e IMAP. Mecanismos de autenticación del remitente: SPF, DKIM y DMARC, reeditado en mayo de 2026 por los RFC 9989, 9990 y 9991">
  <style>.t10{font:700 10px system-ui,sans-serif;fill:#fff}.s10{font:8.5px system-ui,sans-serif;fill:#fff}.d10{font:9px system-ui,sans-serif;fill:#333}.h10{font:700 13px system-ui,sans-serif;fill:#0055a0}.k10{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n10{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h10">SMTP envía y transporta; POP3 e IMAP solo recogen del buzón</text>
  <text x="20" y="42" class="k10">EL CAMINO DE UN MENSAJE</text>
  <rect x="20" y="50" width="146" height="50" rx="5" fill="#0055a0"/><text x="93" y="70" text-anchor="middle" class="t10">MUA emisor</text><text x="93" y="86" text-anchor="middle" class="s10">Cliente o correo web</text>
  <rect x="184" y="50" width="146" height="50" rx="5" fill="#2d8659"/><text x="257" y="70" text-anchor="middle" class="t10">MSA · puerto 587</text><text x="257" y="86" text-anchor="middle" class="s10">Recibe y valida el envío</text>
  <rect x="348" y="50" width="146" height="50" rx="5" fill="#2d8659"/><text x="421" y="70" text-anchor="middle" class="t10">MTA · puerto 25</text><text x="421" y="86" text-anchor="middle" class="s10">Encamina entre dominios</text>
  <rect x="512" y="50" width="146" height="50" rx="5" fill="#e89822"/><text x="585" y="70" text-anchor="middle" class="t10">MDA y buzón</text><text x="585" y="86" text-anchor="middle" class="s10">IMAP 993 · POP3 995</text>
  <path d="M166 76 L180 76" stroke="#666" stroke-width="1.5" marker-end="url(#a10)"/>
  <path d="M330 76 L344 76" stroke="#666" stroke-width="1.5" marker-end="url(#a10)"/>
  <path d="M494 76 L508 76" stroke="#666" stroke-width="1.5" marker-end="url(#a10)"/>
  <defs><marker id="a10" markerWidth="7" markerHeight="7" refX="6" refY="3" orient="auto"><path d="M0,0 L6,3 L0,6 z" fill="#666"/></marker></defs>
  <text x="20" y="122" class="k10">PROTOCOLOS Y PUERTOS</text>
  <rect x="20" y="130" width="206" height="44" rx="4" fill="#eef3f8"/><text x="123" y="146" text-anchor="middle" class="d10">SMTP · RFC 5321 · ENVÍO</text><text x="123" y="161" text-anchor="middle" class="n10">25 servidores · 587 y 465 desde el cliente</text>
  <rect x="237" y="130" width="206" height="44" rx="4" fill="#eef3f8"/><text x="340" y="146" text-anchor="middle" class="d10">POP3 · RFC 1939 · RECOGIDA</text><text x="340" y="161" text-anchor="middle" class="n10">110 y 995 · descarga y borra del servidor</text>
  <rect x="454" y="130" width="206" height="44" rx="4" fill="#eaf5ef"/><text x="557" y="146" text-anchor="middle" class="d10">IMAP · RFC 9051 · RECOGIDA</text><text x="557" y="161" text-anchor="middle" class="n10">143 y 993 · mantiene y sincroniza</text>
  <text x="20" y="196" class="k10">AUTENTICACIÓN DEL REMITENTE · los tres se publican como registros TXT en el DNS</text>
  <rect x="20" y="204" width="206" height="56" rx="5" fill="#0055a0"/><text x="123" y="222" text-anchor="middle" class="t10">SPF · RFC 7208</text><text x="123" y="238" text-anchor="middle" class="s10">Qué servidores pueden</text><text x="123" y="251" text-anchor="middle" class="s10">enviar con ese dominio</text>
  <rect x="237" y="204" width="206" height="56" rx="5" fill="#0055a0"/><text x="340" y="222" text-anchor="middle" class="t10">DKIM · RFC 6376</text><text x="340" y="238" text-anchor="middle" class="s10">FIRMA criptográfica de</text><text x="340" y="251" text-anchor="middle" class="s10">cabeceras y cuerpo</text>
  <rect x="454" y="204" width="206" height="56" rx="5" fill="#2d8659"/><text x="557" y="222" text-anchor="middle" class="t10">DMARC · RFC 9989 (2026)</text><text x="557" y="238" text-anchor="middle" class="s10">Alineamiento, política</text><text x="557" y="251" text-anchor="middle" class="s10">(none, quarantine, reject)</text>
  <rect x="20" y="268" width="640" height="26" rx="4" fill="#fbeaea"/>
  <text x="340" y="285" text-anchor="middle" class="d10">La cabecera From la escribe el emisor y SMTP no la autentica: esa es la raíz técnica de la suplantación y del fraude</text>
  <rect x="20" y="302" width="640" height="34" rx="5" fill="none" stroke="#0055a0" stroke-width="1.5"/>
  <text x="340" y="317" text-anchor="middle" class="k10">Un cliente de correo necesita SIEMPRE dos servidores: uno de salida (SMTP) y uno de entrada (IMAP o POP3)</text>
  <text x="340" y="330" text-anchor="middle" class="n10">La cabecera Bcc no viaja al destinatario: el servidor la elimina · MIME permite acentos, HTML y adjuntos</text>
  <text x="670" y="364" text-anchor="end" class="n10">[Fuente: RFC 5321, RFC 1939, RFC 9051, RFC 9989; ENS mp.s.1]</text>
</svg>
```

---

## D11 · FTP: modo activo, modo pasivo y alternativas seguras

**Sección**: §3.1.2 — Transferencia de archivos
**Propósito**: Explicar por qué FTP usa dos conexiones y en qué se diferencia el modo activo del pasivo, y separar de una vez **FTPS** de **SFTP**.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 364" role="img" aria-label="FTP utiliza dos conexiones TCP: control por el puerto 21 y datos por el 20. En modo activo el servidor abre la conexión de datos hacia el cliente, lo que suele bloquear el cortafuegos; en modo pasivo el cliente abre ambas conexiones, por lo que funciona con NAT y cortafuegos. Alternativas seguras: FTPS es FTP sobre TLS, SFTP es un subsistema de SSH en el puerto 22 y no tiene relación con FTP, y SCP y HTTPS completan el cuadro">
  <style>.t11{font:700 10px system-ui,sans-serif;fill:#fff}.s11{font:8.5px system-ui,sans-serif;fill:#fff}.d11{font:9px system-ui,sans-serif;fill:#333}.h11{font:700 13px system-ui,sans-serif;fill:#0055a0}.k11{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n11{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h11">FTP abre DOS conexiones: quién abre la de datos define el modo</text>
  <text x="20" y="42" class="k11">MODO ACTIVO · el servidor llama al cliente</text>
  <rect x="20" y="50" width="126" height="44" rx="5" fill="#0055a0"/><text x="83" y="68" text-anchor="middle" class="t11">CLIENTE</text><text x="83" y="84" text-anchor="middle" class="s11">Puerto alto</text>
  <rect x="514" y="50" width="126" height="44" rx="5" fill="#0055a0"/><text x="577" y="68" text-anchor="middle" class="t11">SERVIDOR FTP</text><text x="577" y="84" text-anchor="middle" class="s11">Puertos 21 y 20</text>
  <path d="M146 64 L510 64" stroke="#2d8659" stroke-width="1.5" marker-end="url(#a11)"/>
  <text x="328" y="60" text-anchor="middle" class="n11">1 · CONTROL: el cliente abre hacia el puerto 21 (comando PORT)</text>
  <path d="M510 84 L150 84" stroke="#d13c3c" stroke-width="1.5" marker-end="url(#a11b)"/>
  <text x="330" y="80" text-anchor="middle" class="n11">2 · DATOS: el SERVIDOR abre desde su puerto 20 hacia el cliente</text>
  <defs><marker id="a11" markerWidth="7" markerHeight="7" refX="6" refY="3" orient="auto"><path d="M0,0 L6,3 L0,6 z" fill="#2d8659"/></marker><marker id="a11b" markerWidth="7" markerHeight="7" refX="6" refY="3" orient="auto"><path d="M0,0 L6,3 L0,6 z" fill="#d13c3c"/></marker></defs>
  <rect x="20" y="100" width="620" height="24" rx="4" fill="#fbeaea"/><text x="330" y="116" text-anchor="middle" class="d11">Esa conexión ENTRANTE la bloquean normalmente el cortafuegos y el NAT del cliente</text>
  <text x="20" y="146" class="k11">MODO PASIVO · el cliente abre las dos (comando PASV)</text>
  <rect x="20" y="154" width="126" height="44" rx="5" fill="#0055a0"/><text x="83" y="172" text-anchor="middle" class="t11">CLIENTE</text><text x="83" y="188" text-anchor="middle" class="s11">Abre ambas</text>
  <rect x="514" y="154" width="126" height="44" rx="5" fill="#0055a0"/><text x="577" y="172" text-anchor="middle" class="t11">SERVIDOR FTP</text><text x="577" y="188" text-anchor="middle" class="s11">21 y puerto alto</text>
  <path d="M146 168 L510 168" stroke="#2d8659" stroke-width="1.5" marker-end="url(#a11)"/>
  <text x="328" y="164" text-anchor="middle" class="n11">1 · CONTROL hacia el puerto 21</text>
  <path d="M146 188 L510 188" stroke="#2d8659" stroke-width="1.5" marker-end="url(#a11)"/>
  <text x="328" y="184" text-anchor="middle" class="n11">2 · DATOS: el CLIENTE abre hacia el puerto alto que le indica el servidor</text>
  <rect x="20" y="204" width="620" height="24" rx="4" fill="#eaf5ef"/><text x="330" y="220" text-anchor="middle" class="d11">Es el modo que funciona con NAT y cortafuegos, y por eso el habitual hoy</text>
  <text x="20" y="250" class="k11">ALTERNATIVAS SEGURAS · FTP transmite credenciales y datos EN CLARO</text>
  <rect x="20" y="258" width="154" height="44" rx="4" fill="#e89822"/><text x="97" y="276" text-anchor="middle" class="t11">FTPS</text><text x="97" y="292" text-anchor="middle" class="s11">FTP + TLS · 990 o 21</text>
  <rect x="182" y="258" width="154" height="44" rx="4" fill="#2d8659"/><text x="259" y="276" text-anchor="middle" class="t11">SFTP</text><text x="259" y="292" text-anchor="middle" class="s11">Subsistema de SSH · 22</text>
  <rect x="344" y="258" width="154" height="44" rx="4" fill="#eef3f8"/><text x="421" y="276" text-anchor="middle" class="d11">SCP</text><text x="421" y="292" text-anchor="middle" class="n11">Sobre SSH · desaconsejado</text>
  <rect x="506" y="258" width="154" height="44" rx="4" fill="#eef3f8"/><text x="583" y="276" text-anchor="middle" class="d11">HTTPS</text><text x="583" y="292" text-anchor="middle" class="n11">443 · atraviesa cualquier red</text>
  <rect x="20" y="310" width="640" height="26" rx="4" fill="none" stroke="#d13c3c" stroke-width="1.5"/>
  <text x="340" y="327" text-anchor="middle" class="k11">SFTP NO ES FTPS: SFTP es SSH y no tiene ninguna relación con el protocolo FTP</text>
  <text x="670" y="356" text-anchor="end" class="n11">[Fuente: RFC 959; RFC 4251-4254]</text>
</svg>
```

---

## D12 · SSH: arquitectura en tres capas y métodos de autenticación

**Sección**: §3.2.1 — Acceso remoto seguro
**Propósito**: Fijar las tres capas del protocolo, los métodos de autenticación y la confianza en el primer uso, que son los tres puntos preguntables del epígrafe.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 352" role="img" aria-label="Arquitectura de SSH en tres capas: la capa de transporte cifra, comprueba la integridad y autentica al servidor mediante su clave de host; la capa de autenticación de usuario admite contraseña, par de claves, certificado o Kerberos; y la capa de conexión multiplexa canales para sesión interactiva, SFTP y reenvío de puertos. Sustituye a Telnet, rlogin y rsh, que viajan en claro. La primera conexión muestra la huella del servidor bajo el modelo de confianza en el primer uso">
  <style>.t12{font:700 10px system-ui,sans-serif;fill:#fff}.s12{font:8.5px system-ui,sans-serif;fill:#fff}.d12{font:9px system-ui,sans-serif;fill:#333}.h12{font:700 13px system-ui,sans-serif;fill:#0055a0}.k12{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n12{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h12">SSH (puerto 22) sustituye a Telnet, rlogin y rsh, que van en claro</text>
  <text x="20" y="42" class="k12">ARQUITECTURA EN TRES CAPAS · RFC 4251 a 4254</text>
  <rect x="20" y="50" width="640" height="44" rx="5" fill="#2d8659"/><text x="340" y="68" text-anchor="middle" class="t12">3 · CAPA DE CONEXIÓN</text><text x="340" y="84" text-anchor="middle" class="s12">Multiplexa canales sobre una sola conexión: sesión interactiva, ejecución de órdenes, SFTP y reenvío de puertos</text>
  <rect x="20" y="100" width="640" height="44" rx="5" fill="#0055a0"/><text x="340" y="118" text-anchor="middle" class="t12">2 · CAPA DE AUTENTICACIÓN DE USUARIO</text><text x="340" y="134" text-anchor="middle" class="s12">Autentica al CLIENTE ante el servidor</text>
  <rect x="20" y="150" width="640" height="44" rx="5" fill="#7a2f8a"/><text x="340" y="168" text-anchor="middle" class="t12">1 · CAPA DE TRANSPORTE</text><text x="340" y="184" text-anchor="middle" class="s12">Cifrado, integridad y autenticación del SERVIDOR mediante su clave de host</text>
  <text x="20" y="216" class="k12">MÉTODOS DE AUTENTICACIÓN DEL USUARIO, de menor a mayor robustez</text>
  <rect x="20" y="224" width="206" height="42" rx="4" fill="#fbeaea"/><text x="123" y="240" text-anchor="middle" class="d12">Contraseña</text><text x="123" y="255" text-anchor="middle" class="n12">Vulnerable a fuerza bruta</text>
  <rect x="237" y="224" width="206" height="42" rx="4" fill="#eaf5ef"/><text x="340" y="240" text-anchor="middle" class="d12">Par de claves · recomendado</text><text x="340" y="255" text-anchor="middle" class="n12">Clave privada protegida en el cliente</text>
  <rect x="454" y="224" width="206" height="42" rx="4" fill="#eef3f8"/><text x="557" y="240" text-anchor="middle" class="d12">Certificado o Kerberos</text><text x="557" y="255" text-anchor="middle" class="n12">Gestión centralizada de identidades</text>
  <rect x="20" y="274" width="640" height="26" rx="4" fill="#fdf3e3"/>
  <text x="340" y="291" text-anchor="middle" class="d12">CONFIANZA EN EL PRIMER USO: la huella del servidor se guarda en known_hosts; si cambia, el cliente aborta la conexión</text>
  <rect x="20" y="308" width="640" height="24" rx="4" fill="none" stroke="#d13c3c" stroke-width="1.5"/>
  <text x="340" y="324" text-anchor="middle" class="k12">Bastionado: sin acceso directo del superusuario, sin contraseña si hay claves y sin reenvío de puertos</text>
  <text x="670" y="344" text-anchor="end" class="n12">[Fuente: RFC 4251-4254; CCN-STIC serie 500/600]</text>
</svg>
```

---

## D13 · DHCP: intercambio DORA y configuración en IPv6

**Sección**: §3.2.2 — Configuración dinámica de red
**Propósito**: Memorizar la secuencia DORA con sus puertos y contrastar la configuración de IPv4 con las dos vías de IPv6, incluida la consecuencia de SLAAC sobre la trazabilidad.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 364" role="img" aria-label="Intercambio DHCP en cuatro pasos: Discover en difusión desde el cliente, Offer del servidor con una dirección propuesta, Request del cliente aceptando una oferta y Acknowledge del servidor confirmando la concesión. Usa UDP con el puerto 67 en el servidor y el 68 en el cliente, y la concesión se renueva al cincuenta por ciento de su duración. En IPv6 conviven SLAAC sin estado y DHCPv6 con estado en los puertos 546 y 547. Riesgos: servidor DHCP no autorizado, mitigado con DHCP snooping y RA Guard">
  <style>.t13{font:700 10px system-ui,sans-serif;fill:#fff}.s13{font:8.5px system-ui,sans-serif;fill:#fff}.d13{font:9px system-ui,sans-serif;fill:#333}.h13{font:700 13px system-ui,sans-serif;fill:#0055a0}.k13{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n13{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h13">DORA: Discover, Offer, Request y Acknowledge</text>
  <text x="20" y="42" class="k13">EL INTERCAMBIO · UDP, puerto 67 en el servidor y 68 en el cliente</text>
  <rect x="20" y="50" width="154" height="58" rx="5" fill="#0055a0"/><text x="97" y="68" text-anchor="middle" class="t13">1 · DISCOVER</text><text x="97" y="84" text-anchor="middle" class="s13">El cliente, sin dirección,</text><text x="97" y="97" text-anchor="middle" class="s13">emite en DIFUSIÓN</text>
  <rect x="182" y="50" width="154" height="58" rx="5" fill="#2d8659"/><text x="259" y="68" text-anchor="middle" class="t13">2 · OFFER</text><text x="259" y="84" text-anchor="middle" class="s13">Uno o varios servidores</text><text x="259" y="97" text-anchor="middle" class="s13">ofrecen una dirección</text>
  <rect x="344" y="50" width="154" height="58" rx="5" fill="#0055a0"/><text x="421" y="68" text-anchor="middle" class="t13">3 · REQUEST</text><text x="421" y="84" text-anchor="middle" class="s13">El cliente acepta UNA</text><text x="421" y="97" text-anchor="middle" class="s13">oferta, también en difusión</text>
  <rect x="506" y="50" width="154" height="58" rx="5" fill="#2d8659"/><text x="583" y="68" text-anchor="middle" class="t13">4 · ACK</text><text x="583" y="84" text-anchor="middle" class="s13">El servidor confirma la</text><text x="583" y="97" text-anchor="middle" class="s13">concesión y su duración</text>
  <rect x="20" y="118" width="640" height="26" rx="4" fill="#fdf3e3"/>
  <text x="340" y="135" text-anchor="middle" class="d13">Renovación: al 50 % de la concesión (T1) con el mismo servidor y, si no responde, al 87,5 % (T2) con cualquiera</text>
  <text x="20" y="166" class="k13">PIEZAS QUE SE PREGUNTAN</text>
  <rect x="20" y="174" width="312" height="44" rx="4" fill="#eef3f8"/><text x="176" y="190" text-anchor="middle" class="d13">AGENTE DE RETRANSMISIÓN</text><text x="176" y="205" text-anchor="middle" class="n13">Las difusiones no cruzan el encaminador: él reenvía la petición</text>
  <rect x="348" y="174" width="312" height="44" rx="4" fill="#eef3f8"/><text x="504" y="190" text-anchor="middle" class="d13">RESERVA POR DIRECCIÓN MAC</text><text x="504" y="205" text-anchor="middle" class="n13">Dirección estable para impresoras y servidores</text>
  <text x="20" y="240" class="k13">CONFIGURACIÓN EN IPv6 · dos vías que conviven</text>
  <rect x="20" y="248" width="312" height="52" rx="5" fill="#e89822"/><text x="176" y="266" text-anchor="middle" class="t13">SLAAC · SIN ESTADO</text><text x="176" y="282" text-anchor="middle" class="s13">El encaminador anuncia el prefijo (RA) y</text><text x="176" y="295" text-anchor="middle" class="s13">cada equipo se construye su dirección</text>
  <rect x="348" y="248" width="312" height="52" rx="5" fill="#0055a0"/><text x="504" y="266" text-anchor="middle" class="t13">DHCPv6 · CON ESTADO</text><text x="504" y="282" text-anchor="middle" class="s13">RFC 9915 (2026), STD 102 · UDP 547 y 546</text><text x="504" y="295" text-anchor="middle" class="s13">Mantiene registro de las concesiones</text>
  <rect x="20" y="308" width="640" height="26" rx="4" fill="#fbeaea"/>
  <text x="340" y="325" text-anchor="middle" class="d13">Un servidor DHCP no autorizado puede convertirse en intermediario: se mitiga con DHCP snooping y, en IPv6, con RA Guard</text>
  <text x="670" y="356" text-anchor="end" class="n13">[Fuente: RFC 2131, RFC 9915, RFC 4862; ENS mp.com.4]</text>
</svg>
```

---
## D14 · Anatomía de un mensaje HTTP: petición y respuesta

**Sección**: §4.2.1 — Estructura de mensajes, métodos y códigos de respuesta
**Propósito**: Ver las tres partes del mensaje y tener en una sola imagen la clasificación de métodos por seguridad e idempotencia y las cinco familias de códigos de estado.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 372" role="img" aria-label="Estructura de un mensaje HTTP: línea de inicio, cabeceras y, tras una línea en blanco, cuerpo opcional. Ejemplo de petición GET con las cabeceras Host y Cookie y de respuesta 200 OK con Content-Type y Content-Length. Clasificación de métodos: GET, HEAD, OPTIONS y TRACE son seguros e idempotentes; PUT y DELETE son idempotentes pero no seguros; POST y PATCH no son ni seguros ni idempotentes. Familias de códigos de estado del 1xx al 5xx">
  <style>.t14{font:700 10px system-ui,sans-serif;fill:#fff}.s14{font:8.5px system-ui,sans-serif;fill:#fff}.d14{font:9px system-ui,sans-serif;fill:#333}.h14{font:700 13px system-ui,sans-serif;fill:#0055a0}.k14{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n14{font:8.5px system-ui,sans-serif;fill:#666}.m14{font:8.5px ui-monospace,monospace;fill:#333}</style>
  <text x="340" y="20" text-anchor="middle" class="h14">Línea de inicio + cabeceras + línea en blanco + cuerpo opcional</text>
  <text x="20" y="42" class="k14">PETICIÓN</text>
  <text x="348" y="42" class="k14">RESPUESTA</text>
  <rect x="20" y="50" width="312" height="108" rx="5" fill="#eef3f8"/>
  <text x="30" y="68" class="m14">GET /tramites/licencias?id=471 HTTP/1.1</text>
  <text x="30" y="84" class="m14">Host: sede.madrid.es</text>
  <text x="30" y="100" class="m14">Accept: text/html</text>
  <text x="30" y="116" class="m14">Cookie: JSESSIONID=8F2A...</text>
  <text x="30" y="140" class="n14">Línea en blanco y, si el método lo lleva, cuerpo</text>
  <rect x="348" y="50" width="312" height="108" rx="5" fill="#eaf5ef"/>
  <text x="358" y="68" class="m14">HTTP/1.1 200 OK</text>
  <text x="358" y="84" class="m14">Content-Type: text/html; charset=utf-8</text>
  <text x="358" y="100" class="m14">Content-Length: 34871</text>
  <text x="358" y="116" class="m14">Cache-Control: no-store</text>
  <text x="358" y="140" class="n14">Línea en blanco y cuerpo con el documento</text>
  <text x="20" y="180" class="k14">MÉTODOS · seguro = no modifica el estado · idempotente = repetirlo da el mismo efecto</text>
  <rect x="20" y="188" width="206" height="46" rx="5" fill="#2d8659"/><text x="123" y="206" text-anchor="middle" class="t14">SEGUROS E IDEMPOTENTES</text><text x="123" y="222" text-anchor="middle" class="s14">GET · HEAD · OPTIONS · TRACE</text>
  <rect x="237" y="188" width="206" height="46" rx="5" fill="#e89822"/><text x="340" y="206" text-anchor="middle" class="t14">SOLO IDEMPOTENTES</text><text x="340" y="222" text-anchor="middle" class="s14">PUT · DELETE</text>
  <rect x="454" y="188" width="206" height="46" rx="5" fill="#d13c3c"/><text x="557" y="206" text-anchor="middle" class="t14">NI SEGUROS NI IDEMPOTENTES</text><text x="557" y="222" text-anchor="middle" class="s14">POST · PATCH</text>
  <text x="20" y="254" class="k14">CÓDIGOS DE ESTADO · la primera cifra manda</text>
  <rect x="20" y="262" width="120" height="48" rx="4" fill="#eef3f8"/><text x="80" y="280" text-anchor="middle" class="d14">1xx</text><text x="80" y="295" text-anchor="middle" class="n14">Informativo</text>
  <rect x="150" y="262" width="120" height="48" rx="4" fill="#eaf5ef"/><text x="210" y="280" text-anchor="middle" class="d14">2xx · éxito</text><text x="210" y="295" text-anchor="middle" class="n14">200 · 201 · 204</text>
  <rect x="280" y="262" width="120" height="48" rx="4" fill="#fdf3e3"/><text x="340" y="280" text-anchor="middle" class="d14">3xx · redirección</text><text x="340" y="295" text-anchor="middle" class="n14">301 · 302 · 304</text>
  <rect x="410" y="262" width="120" height="48" rx="4" fill="#fbeaea"/><text x="470" y="280" text-anchor="middle" class="d14">4xx · cliente</text><text x="470" y="295" text-anchor="middle" class="n14">400 · 401 · 403 · 404</text>
  <rect x="540" y="262" width="120" height="48" rx="4" fill="#fbeaea"/><text x="600" y="280" text-anchor="middle" class="d14">5xx · servidor</text><text x="600" y="295" text-anchor="middle" class="n14">500 · 502 · 503 · 504</text>
  <rect x="20" y="316" width="640" height="34" rx="5" fill="none" stroke="#0055a0" stroke-width="1.5"/>
  <text x="340" y="331" text-anchor="middle" class="k14">401 = NO AUTENTICADO · 403 = autenticado pero SIN PERMISO · 301 permanente y cacheada · 302 y 307 temporales</text>
  <text x="340" y="344" text-anchor="middle" class="n14">POST no cifra nada: solo evita que el dato quede escrito en la URL; lo que protege el contenido es HTTPS</text>
  <text x="670" y="364" text-anchor="end" class="n14">[Fuente: RFC 9110 y RFC 9112]</text>
</svg>
```

---

## D15 · De HTTP/0.9 a HTTP/3: qué resuelve cada versión

**Sección**: §4.1.2 — Evolución desde HTTP/1.1 hasta HTTP/3
**Propósito**: Encadenar las cinco versiones por el problema que cada una resolvió y el que dejó abierto, con el bloqueo de cabecera de línea como hilo conductor.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 372" role="img" aria-label="Evolución de HTTP: la versión 0.9 de 1991 solo servía documentos; la 1.0 de 1996 añadió cabeceras y códigos de estado pero abría una conexión por recurso; la 1.1 introdujo conexiones persistentes y la cabecera Host obligatoria pero sufre bloqueo de cabecera de línea en la aplicación; HTTP/2 es binario y multiplexado con compresión HPACK pero mantiene el bloqueo en TCP; HTTP/3 se apoya en QUIC sobre UDP con cifrado obligatorio y elimina el bloqueo del transporte">
  <style>.t15{font:700 10px system-ui,sans-serif;fill:#fff}.s15{font:8.5px system-ui,sans-serif;fill:#fff}.d15{font:9px system-ui,sans-serif;fill:#333}.h15{font:700 13px system-ui,sans-serif;fill:#0055a0}.k15{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n15{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h15">Cada versión de HTTP resuelve el cuello de botella de la anterior</text>
  <text x="20" y="42" class="k15">VERSIÓN</text>
  <text x="136" y="42" class="k15">QUÉ APORTA</text>
  <text x="442" y="42" class="k15">QUÉ PROBLEMA DEJA ABIERTO</text>
  <rect x="20" y="50" width="110" height="44" rx="4" fill="#888"/><text x="75" y="70" text-anchor="middle" class="t15">HTTP/0.9</text><text x="75" y="85" text-anchor="middle" class="s15">1991</text>
  <rect x="136" y="50" width="300" height="44" rx="4" fill="#eef3f8"/><text x="286" y="70" text-anchor="middle" class="d15">Una sola línea: GET /pagina</text><text x="286" y="85" text-anchor="middle" class="n15">Sin cabeceras, sin códigos de estado, sin versiones</text>
  <rect x="442" y="50" width="218" height="44" rx="4" fill="#fbeaea"/><text x="551" y="76" text-anchor="middle" class="n15">Solo sirve documentos HTML</text>
  <rect x="20" y="100" width="110" height="44" rx="4" fill="#888"/><text x="75" y="120" text-anchor="middle" class="t15">HTTP/1.0</text><text x="75" y="135" text-anchor="middle" class="s15">1996 · RFC 1945</text>
  <rect x="136" y="100" width="300" height="44" rx="4" fill="#eef3f8"/><text x="286" y="120" text-anchor="middle" class="d15">Cabeceras, códigos de estado y MIME</text><text x="286" y="135" text-anchor="middle" class="n15">Aparecen los métodos HEAD y POST</text>
  <rect x="442" y="100" width="218" height="44" rx="4" fill="#fbeaea"/><text x="551" y="126" text-anchor="middle" class="n15">Una conexión TCP por cada recurso</text>
  <rect x="20" y="150" width="110" height="44" rx="4" fill="#0055a0"/><text x="75" y="170" text-anchor="middle" class="t15">HTTP/1.1</text><text x="75" y="185" text-anchor="middle" class="s15">RFC 9112 · STD 99</text>
  <rect x="136" y="150" width="300" height="44" rx="4" fill="#eef3f8"/><text x="286" y="170" text-anchor="middle" class="d15">Conexiones persistentes y Host obligatoria</text><text x="286" y="185" text-anchor="middle" class="n15">Alojamiento virtual, rangos, caché y chunked</text>
  <rect x="442" y="150" width="218" height="44" rx="4" fill="#fbeaea"/><text x="551" y="170" text-anchor="middle" class="n15">Bloqueo de cabecera de línea</text><text x="551" y="184" text-anchor="middle" class="n15">en la APLICACIÓN: respuestas en orden</text>
  <rect x="20" y="200" width="110" height="44" rx="4" fill="#2d8659"/><text x="75" y="220" text-anchor="middle" class="t15">HTTP/2</text><text x="75" y="235" text-anchor="middle" class="s15">2015 · RFC 9113</text>
  <rect x="136" y="200" width="300" height="44" rx="4" fill="#eaf5ef"/><text x="286" y="220" text-anchor="middle" class="d15">Binario y multiplexado sobre UNA conexión</text><text x="286" y="235" text-anchor="middle" class="n15">Compresión de cabeceras HPACK y priorización</text>
  <rect x="442" y="200" width="218" height="44" rx="4" fill="#fbeaea"/><text x="551" y="220" text-anchor="middle" class="n15">Persiste el bloqueo en TCP: un</text><text x="551" y="234" text-anchor="middle" class="n15">segmento perdido detiene TODO</text>
  <rect x="20" y="250" width="110" height="44" rx="4" fill="#2d8659"/><text x="75" y="270" text-anchor="middle" class="t15">HTTP/3</text><text x="75" y="285" text-anchor="middle" class="s15">2022 · RFC 9114</text>
  <rect x="136" y="250" width="300" height="44" rx="4" fill="#eaf5ef"/><text x="286" y="270" text-anchor="middle" class="d15">Sobre QUIC (RFC 9000) y UDP</text><text x="286" y="285" text-anchor="middle" class="n15">Cifrado obligatorio, QPACK, 1-RTT y migración</text>
  <rect x="442" y="250" width="218" height="44" rx="4" fill="#fdf3e3"/><text x="551" y="270" text-anchor="middle" class="n15">Exige UDP abierto y dificulta la</text><text x="551" y="284" text-anchor="middle" class="n15">inspección en equipos intermedios</text>
  <rect x="20" y="304" width="640" height="42" rx="5" fill="none" stroke="#0055a0" stroke-width="1.5"/>
  <text x="340" y="320" text-anchor="middle" class="k15">La semántica es la MISMA en las tres versiones vigentes: métodos, códigos y cabeceras no cambian</text>
  <text x="340" y="334" text-anchor="middle" class="n15">Lo que cambia es cómo se transmiten · HTTP/2 se negocia por ALPN dentro de TLS y HTTP/3 se anuncia con Alt-Svc</text>
  <text x="670" y="364" text-anchor="end" class="n15">[Fuente: RFC 9110 a RFC 9114; RFC 9000]</text>
</svg>
```

---

## D16 · El estado en HTTP: cookies, sesiones y atributos de seguridad

**Sección**: §4.2.2 — Cabeceras HTTP, cookies y sesiones
**Propósito**: Mostrar cómo se construye estado sobre un protocolo que no lo tiene, y fijar qué amenaza mitiga cada atributo de la cookie.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 356" role="img" aria-label="Mecanismo de estado en HTTP: el servidor envía la cabecera Set-Cookie y el navegador devuelve la cabecera Cookie en cada petición posterior. Atributos de seguridad: Secure obliga a HTTPS, HttpOnly impide el acceso desde JavaScript y mitiga el robo por XSS, SameSite mitiga la falsificación de petición en sitios cruzados y Expires determina si la cookie es de sesión o persistente. Comparación entre sesión en el servidor, revocable, y token autocontenido, sin estado pero no revocable">
  <style>.t16{font:700 10px system-ui,sans-serif;fill:#fff}.s16{font:8.5px system-ui,sans-serif;fill:#fff}.d16{font:9px system-ui,sans-serif;fill:#333}.h16{font:700 13px system-ui,sans-serif;fill:#0055a0}.k16{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n16{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h16">HTTP no tiene estado: el estado se transporta en cada petición</text>
  <text x="20" y="42" class="k16">EL MECANISMO</text>
  <rect x="20" y="50" width="150" height="44" rx="5" fill="#0055a0"/><text x="95" y="70" text-anchor="middle" class="t16">NAVEGADOR</text><text x="95" y="85" text-anchor="middle" class="s16">Guarda la cookie</text>
  <rect x="510" y="50" width="150" height="44" rx="5" fill="#0055a0"/><text x="585" y="70" text-anchor="middle" class="t16">SERVIDOR</text><text x="585" y="85" text-anchor="middle" class="s16">Identifica la sesión</text>
  <path d="M506 62 L176 62" stroke="#2d8659" stroke-width="1.5" marker-end="url(#a16)"/>
  <text x="341" y="58" text-anchor="middle" class="n16">1 · Set-Cookie: JSESSIONID=8F2A...; Secure; HttpOnly; SameSite=Lax</text>
  <path d="M176 84 L506 84" stroke="#0055a0" stroke-width="1.5" marker-end="url(#a16b)"/>
  <text x="341" y="80" text-anchor="middle" class="n16">2 · Cookie: JSESSIONID=8F2A... en TODAS las peticiones siguientes</text>
  <defs><marker id="a16" markerWidth="7" markerHeight="7" refX="6" refY="3" orient="auto"><path d="M0,0 L6,3 L0,6 z" fill="#2d8659"/></marker><marker id="a16b" markerWidth="7" markerHeight="7" refX="6" refY="3" orient="auto"><path d="M0,0 L6,3 L0,6 z" fill="#0055a0"/></marker></defs>
  <text x="20" y="118" class="k16">ATRIBUTOS DE SEGURIDAD · qué amenaza mitiga cada uno</text>
  <rect x="20" y="126" width="154" height="48" rx="4" fill="#2d8659"/><text x="97" y="144" text-anchor="middle" class="t16">Secure</text><text x="97" y="160" text-anchor="middle" class="s16">Solo se envía por HTTPS</text>
  <rect x="182" y="126" width="154" height="48" rx="4" fill="#2d8659"/><text x="259" y="144" text-anchor="middle" class="t16">HttpOnly</text><text x="259" y="160" text-anchor="middle" class="s16">Invisible a JavaScript: XSS</text>
  <rect x="344" y="126" width="154" height="48" rx="4" fill="#2d8659"/><text x="421" y="144" text-anchor="middle" class="t16">SameSite</text><text x="421" y="160" text-anchor="middle" class="s16">Peticiones cruzadas: CSRF</text>
  <rect x="506" y="126" width="154" height="48" rx="4" fill="#e89822"/><text x="583" y="144" text-anchor="middle" class="t16">Expires y Max-Age</text><text x="583" y="160" text-anchor="middle" class="s16">Sesión o persistente</text>
  <text x="20" y="196" class="k16">DÓNDE VIVE EL ESTADO</text>
  <rect x="20" y="204" width="312" height="56" rx="5" fill="#eef3f8"/><text x="176" y="222" text-anchor="middle" class="d16">SESIÓN EN EL SERVIDOR</text><text x="176" y="238" text-anchor="middle" class="n16">La cookie solo lleva un identificador opaco</text><text x="176" y="252" text-anchor="middle" class="n16">Ventaja: se puede REVOCAR al instante</text>
  <rect x="348" y="204" width="312" height="56" rx="5" fill="#fdf3e3"/><text x="504" y="222" text-anchor="middle" class="d16">TOKEN AUTOCONTENIDO (JWT)</text><text x="504" y="238" text-anchor="middle" class="n16">El testigo lleva la información firmada</text><text x="504" y="252" text-anchor="middle" class="n16">Firmado NO es cifrado, y no se revoca sin lista</text>
  <rect x="20" y="270" width="640" height="26" rx="4" fill="#fbeaea"/>
  <text x="340" y="287" text-anchor="middle" class="d16">Para datos personales: Cache-Control no-store (no basta no-cache, que solo obliga a revalidar) y private</text>
  <rect x="20" y="304" width="640" height="26" rx="4" fill="none" stroke="#0055a0" stroke-width="1.5"/>
  <text x="340" y="321" text-anchor="middle" class="k16">Mínimo en un servicio público: Secure + HttpOnly + SameSite, identificador aleatorio y renovado tras el acceso</text>
  <text x="670" y="348" text-anchor="end" class="n16">[Fuente: RFC 6265 y RFC 9111]</text>
</svg>
```

---
## D17 · TLS: subprotocolos y saludo 1.2 frente a 1.3

**Sección**: §5.1.1 — Arquitectura, subprotocolos y negociación TLS
**Propósito**: Fijar que el **Record** es el subprotocolo que encapsula a todos los demás, y comparar los dos viajes del saludo de TLS 1.2 con el único de TLS 1.3.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 372" role="img" aria-label="Arquitectura de TLS: el protocolo Record encapsula a los subprotocolos Handshake, Alert, Change Cipher Spec y los datos de aplicación. Comparación del saludo: TLS 1.2 necesita dos vueltas completas mientras que TLS 1.3 lo resuelve en una sola vuelta porque el cliente envía ya su parte del intercambio Diffie-Hellman en el primer mensaje. Novedades de TLS 1.3: confidencialidad directa obligatoria, solo cifrado autenticado AEAD, sin RSA estático, sin renegociación y sin compresión. Estado de las versiones: SSL prohibido, TLS 1.0 y 1.1 obsoletos, TLS 1.2 y 1.3 vigentes">
  <style>.t17{font:700 10px system-ui,sans-serif;fill:#fff}.s17{font:8.5px system-ui,sans-serif;fill:#fff}.d17{font:9px system-ui,sans-serif;fill:#333}.h17{font:700 13px system-ui,sans-serif;fill:#0055a0}.k17{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n17{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h17">El Record transporta a todos los demás; el Handshake acuerda las claves</text>
  <text x="20" y="42" class="k17">ARQUITECTURA · los subprotocolos viajan DENTRO del Record</text>
  <rect x="20" y="50" width="154" height="34" rx="4" fill="#0055a0"/><text x="97" y="71" text-anchor="middle" class="t17">HANDSHAKE</text>
  <rect x="182" y="50" width="154" height="34" rx="4" fill="#0055a0"/><text x="259" y="71" text-anchor="middle" class="t17">ALERT</text>
  <rect x="344" y="50" width="154" height="34" rx="4" fill="#888"/><text x="421" y="71" text-anchor="middle" class="t17">CHANGE CIPHER SPEC</text>
  <rect x="506" y="50" width="154" height="34" rx="4" fill="#2d8659"/><text x="583" y="71" text-anchor="middle" class="t17">DATOS DE APLICACIÓN</text>
  <rect x="20" y="88" width="640" height="36" rx="4" fill="#7a2f8a"/><text x="340" y="104" text-anchor="middle" class="t17">RECORD PROTOCOL · fragmenta, cifra y protege la integridad de todo lo anterior</text><text x="340" y="118" text-anchor="middle" class="s17">Es el subprotocolo de más bajo nivel: en TLS 1.3 el Change Cipher Spec solo se conserva por compatibilidad</text>
  <text x="20" y="148" class="k17">EL SALUDO</text>
  <rect x="20" y="156" width="312" height="86" rx="5" fill="#eef3f8"/>
  <text x="176" y="174" text-anchor="middle" class="d17">TLS 1.2 · DOS VUELTAS (2-RTT)</text>
  <text x="30" y="192" class="n17">1 · ClientHello: versiones, aleatorio y suites</text>
  <text x="30" y="206" class="n17">2 · ServerHello + Certificate (EN CLARO) + Done</text>
  <text x="30" y="220" class="n17">3 · ClientKeyExchange + ChangeCipherSpec + Finished</text>
  <text x="30" y="234" class="n17">4 · ChangeCipherSpec + Finished del servidor</text>
  <rect x="348" y="156" width="312" height="86" rx="5" fill="#eaf5ef"/>
  <text x="504" y="174" text-anchor="middle" class="d17">TLS 1.3 · UNA VUELTA (1-RTT)</text>
  <text x="358" y="192" class="n17">1 · ClientHello + key_share: el cliente ya envía</text>
  <text x="358" y="206" class="n17">     su parte del Diffie-Hellman efímero</text>
  <text x="358" y="220" class="n17">2 · ServerHello + certificado YA CIFRADO + Finished</text>
  <text x="358" y="234" class="n17">Reanudación posterior: 0-RTT (solo si es idempotente)</text>
  <text x="20" y="264" class="k17">NOVEDADES DE TLS 1.3 · las tres más preguntadas de las cinco</text>
  <rect x="20" y="272" width="206" height="44" rx="4" fill="#2d8659"/><text x="123" y="290" text-anchor="middle" class="t17">CONFIDENCIALIDAD DIRECTA</text><text x="123" y="306" text-anchor="middle" class="s17">Obligatoria: solo ECDHE o DHE</text>
  <rect x="237" y="272" width="206" height="44" rx="4" fill="#2d8659"/><text x="340" y="290" text-anchor="middle" class="t17">SOLO CIFRADO AEAD</text><text x="340" y="306" text-anchor="middle" class="s17">Sin RC4, 3DES ni compresión</text>
  <rect x="454" y="272" width="206" height="44" rx="4" fill="#2d8659"/><text x="557" y="290" text-anchor="middle" class="t17">SIN RSA NI RENEGOCIACIÓN</text><text x="557" y="306" text-anchor="middle" class="s17">RSA sigue valiendo para FIRMAR</text>
  <rect x="20" y="324" width="640" height="26" rx="4" fill="#fbeaea"/>
  <text x="340" y="341" text-anchor="middle" class="d17">SSL 2.0 y 3.0 PROHIBIDOS · TLS 1.0 y 1.1 OBSOLETOS (RFC 8996) · vigentes TLS 1.2 y TLS 1.3 (RFC 9846, julio de 2026)</text>
  <text x="670" y="364" text-anchor="end" class="n17">[Fuente: RFC 9846, RFC 8996, RFC 7568; CCN-STIC-807]</text>
</svg>
```

---

## D18 · HTTPS de extremo a extremo en una sede electrónica

**Sección**: §5.2.1 — Funcionamiento de HTTP sobre TLS · §6.1.1
**Propósito**: Recorrer la conexión completa desde que se escribe el nombre hasta que llega la página cifrada, señalando el único momento de riesgo y la medida del ENS que ampara cada pieza.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 384" role="img" aria-label="Conexión HTTPS completa a una sede electrónica: resolución DNS del nombre, conexión TCP, redirección 301 de HTTP a HTTPS que es el único momento en claro y que elimina la precarga de HSTS, saludo TLS con el nombre del servidor en la extensión SNI, validación de la cadena del certificado comprobando firma, vigencia, nombre alternativo y revocación, y finalmente la petición HTTP cifrada y la respuesta con la cabecera HSTS. Se indican las medidas del Esquema Nacional de Seguridad aplicables: mp punto com punto 2 y 3, mp punto s punto 2 y op punto exp punto 10">
  <style>.t18{font:700 10px system-ui,sans-serif;fill:#fff}.s18{font:8.5px system-ui,sans-serif;fill:#fff}.d18{font:9px system-ui,sans-serif;fill:#333}.h18{font:700 13px system-ui,sans-serif;fill:#0055a0}.k18{font:700 9.5px system-ui,sans-serif;fill:#0055a0}.n18{font:8.5px system-ui,sans-serif;fill:#666}</style>
  <text x="340" y="20" text-anchor="middle" class="h18">HTTPS no es otro protocolo: es HTTP dentro de TLS, en el puerto 443</text>
  <text x="20" y="42" class="k18">EL ORDEN DE LAS CAPAS · TCP primero, TLS después, HTTP al final</text>
  <rect x="20" y="50" width="206" height="34" rx="4" fill="#7a2f8a"/><text x="123" y="71" text-anchor="middle" class="t18">1 · TCP · saludo en tres pasos</text>
  <rect x="237" y="50" width="206" height="34" rx="4" fill="#0055a0"/><text x="340" y="71" text-anchor="middle" class="t18">2 · TLS · saludo y claves</text>
  <rect x="454" y="50" width="206" height="34" rx="4" fill="#2d8659"/><text x="557" y="71" text-anchor="middle" class="t18">3 · HTTP · ya cifrado</text>
  <text x="20" y="106" class="k18">LA CONEXIÓN COMPLETA A sede.madrid.es</text>
  <rect x="20" y="114" width="640" height="26" rx="4" fill="#eef3f8"/><circle cx="38" cy="127" r="9" fill="#0055a0"/><text x="38" y="130" text-anchor="middle" class="t18">1</text><text x="56" y="131" class="d18">DNS: se resuelve el nombre en una dirección IP (con DoT o DoH la consulta va cifrada)</text>
  <rect x="20" y="144" width="640" height="26" rx="4" fill="#fbeaea"/><circle cx="38" cy="157" r="9" fill="#d13c3c"/><text x="38" y="160" text-anchor="middle" class="t18">2</text><text x="56" y="161" class="d18">Si la petición sale por HTTP/80, el servidor responde 301 · ÚNICO MOMENTO EN CLARO Y ÚNICO RIESGO</text>
  <rect x="20" y="174" width="640" height="26" rx="4" fill="#eef3f8"/><circle cx="38" cy="187" r="9" fill="#0055a0"/><text x="38" y="190" text-anchor="middle" class="t18">3</text><text x="56" y="191" class="d18">TCP/443 y saludo TLS: el cliente envía el nombre del sitio en la extensión SNI, que viaja EN CLARO</text>
  <rect x="20" y="204" width="640" height="26" rx="4" fill="#eef3f8"/><circle cx="38" cy="217" r="9" fill="#0055a0"/><text x="38" y="220" text-anchor="middle" class="t18">4</text><text x="56" y="221" class="d18">Validación de la cadena: firma de la AC, vigencia, nombre en el SAN, restricciones básicas y revocación</text>
  <rect x="20" y="234" width="640" height="26" rx="4" fill="#eaf5ef"/><circle cx="38" cy="247" r="9" fill="#2d8659"/><text x="38" y="250" text-anchor="middle" class="t18">5</text><text x="56" y="251" class="d18">Petición HTTP cifrada; la respuesta incluye HSTS, que evita el paso 2 en las visitas siguientes</text>
  <text x="20" y="282" class="k18">REFUERZOS Y RESPALDO NORMATIVO</text>
  <rect x="20" y="290" width="154" height="44" rx="4" fill="#fdf3e3"/><text x="97" y="306" text-anchor="middle" class="d18">HSTS y precarga</text><text x="97" y="321" text-anchor="middle" class="n18">Elimina el riesgo del paso 2</text>
  <rect x="182" y="290" width="154" height="44" rx="4" fill="#fdf3e3"/><text x="259" y="306" text-anchor="middle" class="d18">CAA y CT</text><text x="259" y="321" text-anchor="middle" class="n18">Qué AC puede emitir y qué emitió</text>
  <rect x="344" y="290" width="154" height="44" rx="4" fill="#eef3f8"/><text x="421" y="306" text-anchor="middle" class="d18">mp.com.2 y mp.com.3</text><text x="421" y="321" text-anchor="middle" class="n18">Cifrado e integridad del canal</text>
  <rect x="506" y="290" width="154" height="44" rx="4" fill="#eef3f8"/><text x="583" y="306" text-anchor="middle" class="d18">mp.s.2 y op.exp.10</text><text x="583" y="321" text-anchor="middle" class="n18">Auditoría web y claves</text>
  <rect x="20" y="338" width="640" height="26" rx="4" fill="none" stroke="#d13c3c" stroke-width="1.5"/>
  <text x="340" y="355" text-anchor="middle" class="k18">HTTPS oculta el contenido, las cabeceras y la ruta; NO oculta la IP de destino ni el SNI, salvo con ECH</text>
  <text x="670" y="376" text-anchor="end" class="n18">[Fuente: RFC 9110, RFC 6797; ENS anexo II; Ley 40/2015, art. 38]</text>
</svg>
```
