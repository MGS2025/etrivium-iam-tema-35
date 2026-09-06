# Tema 35 — Changelog

> **Título oficial**: Internet: arquitectura de red. Origen, evolución y estado actual. Principales servicios. Protocolos HTTP, HTTPS y SSL/TLS.

---

## v1.2 — 2026-09-06 — Marcado del apartado complementario

**Estado**: pendiente de validación por el IAM.

**Motivo**: criterio de literalidad del título fijado por el IAM (Jesús Cuadrado, 02-09-2026).

### Alcance

- El apartado final que **el enunciado oficial del tema no nombra** queda marcado como **material complementario**, en el índice y al principio del propio apartado, con la advertencia de que lo exigible es lo que enumera el título.
- **Sin cambios de contenido**: el apartado se mantiene íntegro.

---

## v1.1 — 2026-09-06 — Ficha de extensión y tiempo de estudio

**Estado**: sin cambios de contenido. Solo se añade información sobre el propio tema.

**Motivo**: petición del IAM (Jesús Cuadrado, 02-09-2026) al validar el Tema 30. Acepta la extensión de los temas «compuestos» a condición de que se informe de «su extensión en palabras y tiempo estimado de estudio». Al revisarlo se vio que ese dato solo aparecía en 16 de los 40 temas, y que faltaba justo en los más largos.

### Alcance

- Ficha bajo la cabecera del tema, y al final de la pestaña Índice donde esa pestaña existe:
  - **Extensión**: ~20.500 palabras · 18 diagramas · 60 preguntas de test
  - **Tiempo estimado de estudio**: 19-21 horas (primera vuelta completa, sin contar repasos)
- La cifra de palabras de la tabla de entregables se sincroniza con la ficha, para que el tema no muestre dos recuentos distintos.
- Las horas salen de una fórmula común a los 40 temas, para que sean comparables entre sí: contenido a 1.500 palabras/hora (ritmo de estudio activo), diagramas a una hora por cada cinco y test a dos minutos por pregunta. Se publica como intervalo de dos horas.
- Generado con `_tools-qa/ficha_estudio.py`, idempotente y reejecutable tras cualquier regeneración con `build_tNN.py`.

---

## v1.0 — 2026-08-27 — Primera versión

Generación completa del tema desde el esqueleto oficial `Test_Prompting/temas agosto/35.md`, siguiendo el patrón de la serie técnica (plantilla de referencia: **T32**).

### Alcance de la v1.0

| Entregable | Cantidad |
|---|---|
| Contenido teórico | 6 secciones · 12 subsecciones · 21 epígrafes · **≈ 18.600 palabras** |
| Diagramas SVG inline | **18** |
| Banco de test | **60 preguntas** A/B/C, balanceadas **20/20/20** |
| Casos prácticos | **3**, de 10 puntos cada uno |
| Fuentes | 60 Tier 1 · 18 Tier 2 · 3 Tier 3 |
| Pestañas del `index.html` | 8 (Inicio, Contenido, Índice, Diagramas, Test, Casos, Validación, Fuentes) |

### Decisiones de generación

1. **Estructura literal del esqueleto, sin ajustes.** Es el **primer esqueleto de la serie de agosto que encaja sin retoques** en los tres niveles de numeración (`N`, `N.M`, `N.M.K`): sus seis bloques, sus doce subapartados y sus veintiún epígrafes se corresponden uno a uno con el contenido. No se repite, por tanto, el problema de mapeo de los Temas 27 y 30.

2. **La frontera con el Tema 34 se declara desde las «Convenciones» y vertebra todo el tema.** Criterio aplicado: **el T34 explica los protocolos** (cabeceras, control de congestión, ARP, ICMP) y **el T35 explica cómo esos protocolos construyen Internet** (sistemas autónomos, BGP, puntos neutros, agotamiento de IPv4, DNS). Por eso §2.1 presenta la pila como marco de referencia y §2.2 desarrolla a fondo el encaminamiento interdominio y el DNS. Anotado como punto 1 de validación.

3. **⚠️ Hallazgo de la verificación de fuentes: el RFC 8446 ya no es la referencia vigente de TLS 1.3.** Al contrastar los RFC contra el **índice oficial del RFC Editor** —y no de memoria— se detectó que el **RFC 8446 fue obsoletado por el RFC 9846 el pasado julio de 2026**, un mes antes de generar este tema, y que ese mismo RFC 9846 obsoleta también el **RFC 5246 (TLS 1.2)**. Se comprobó después en el propio texto del RFC 9846 que **no prohíbe TLS 1.2**: unifica la especificación y añade requisitos para sus implementaciones. El tema explica ambas cosas y conserva la mención del RFC 8446, que es lo que recogen los temarios al uso. **Prácticamente ningún material de oposición recoge todavía este dato.**

4. **Otros dos hallazgos de la misma verificación**: **DHCPv6** se reeditó en **enero de 2026** como **RFC 9915** (**STD 102**, obsoleta el RFC 8415), y **DMARC** se reeditó en **mayo de 2026** en los **RFC 9989, 9990 y 9991**, que obsoletan el RFC 7489 y lo elevan de *Informational* a *Standards Track*.

5. **Medidas del ENS verificadas contra el PDF del BOE** (`BOE-A-2022-7191`, extraído con `pdftotext -layout`): denominaciones y tablas de aplicación literales de **`mp.com.1`** a **`mp.com.4`** y de **`mp.s.1`** a **`mp.s.4`**, más `mp.si.2`, `mp.eq.4`, `op.acc.4-6` y `op.exp.10`. De ahí sale el dato de que **`mp.s.2` exige auditoría del servicio web `[R1 o R2]` ya en categoría BÁSICA**, que es el eje de §6.

6. **Cifras del «estado actual» verificadas una a una en la fuente que las publica**, con fecha, por ser el bloque más volátil del tema: **IPv6 supera el 50 % el 28-3-2026** (Google) con España en torno al **10 %**; **6.000 millones de usuarios** (UIT, 2025); **HTTP/3 en el 39,5 %** de los sitios (W3Techs, junio de 2026); **más del 95 % de cargas por HTTPS** en Chrome; **2.226.598 dominios `.es`** (Red.es, 6-8-2026); **más de 2.000 instancias** de servidor raíz y **1.348 de 1.437 TLD firmados** con DNSSEC; **ESPANIX** (13-5-1997) con picos superiores a **2 Tbps** y **DE-CIX Madrid** por encima de **1,5 Tbit/s**; calendario **SC-081v3** del CA/Browser Forum (**200 días desde el 15-3-2026**).

7. **Sin fragmentos de código**, como en T26, T28, T29, T30, T31 y T32: lo memorizable son puertos, RFC, códigos de estado y fechas. Sí se incluyen tres bloques literales no ejecutables —descomposición de una URL, mensaje HTTP de petición y de respuesta, y una suite de cifrado desmenuzada— por ser objeto directo de pregunta.

8. **Secuencia de letras del test fijada antes de redactar.** Aplicando la lección de T23, se definió de antemano la secuencia de 60 respuestas con 20 de cada letra. Resultado: **20/20/20 a la primera**, verificado por script.

9. **Tabla de puertos como pieza central de §3**, presentada explícitamente como «la tabla más rentable de todo el tema».

### QA realizado

- **Integridad del test**: 60 preguntas, 3 opciones únicas por pregunta, **coincidencia exacta** entre el texto de la opción correcta y el de la solución, explicación y referencia en las 60. Distribución **20 A / 20 B / 20 C**.
- **Motor de test probado sobre HTTP** (no sobre `file://`): 60 preguntas y 180 opciones renderizadas, 8 pestañas, penalización comprobada (6 aciertos − 3 fallos = **5,00**), corrección y reinicio.
- **SVG**: validación **XML previa** de los 18 diagramas (0 mal formados) y sonda `getBBox` sobre render real: **0 desbordes del `viewBox` y 0 colisiones**.
- **⚠️ Mejora incorporada a la herramienta de QA del proyecto**: `_tools-qa/qa_svg.py` **no incluía el tercer chequeo** descubierto en T30 —texto que se solapa con un `<rect>` sin estar contenido en él, que es como se colaron las atribuciones dibujadas por detrás de cajas con `fill="none"`—. Se ha **añadido al script**, de modo que a partir de ahora se ejecuta en todos los temas. En el T35 no encontró ningún fallo.
- **Revisión visual de los 18 diagramas** por captura a 2×. Cazó **dos fallos que el QA programático no ve**: el rótulo «LAS CINCO NOVEDADES DE TLS 1.3» del **D17** encabezaba solo tres cajas, y la flecha de bajada del **D6** apuntaba al hueco entre dos cajas en lugar de al AS del Ayuntamiento. Ambos corregidos.
- **Markdown crudo filtrado al HTML**: detectadas **dos tablas dentro de callouts** (la de puertos de §3 y la de versiones de TLS de §5.1.1) que el conversor no transforma, porque el bloque de cita se colapsa en un solo párrafo. **Sacadas del callout**; recuento posterior: **0 filas `|---` crudas**, 0 encabezados de markdown crudos y **49 tablas HTML** correctas.
- **Asteriscos crudos**: 3 en el HTML final, los tres **legítimos** —dos de la llamada a nota al pie `(*)` sobre la ubicación de ARP y uno del comodín `*.madrid.es` dentro de un `<code>`—. Se corrigió además un `\*` escapado que el conversor dejaba visible.
- **Ortografía**: hunspell es_ES sobre la prosa y, por separado, sobre el **texto visible y los `aria-label` de los 18 SVG**. Sin errores reales: todos los avisos son vocabulario técnico inglés, siglas o neologismos del dominio.
- **Referencias cruzadas**: 12 temas citados (T22, T23, T25, T29, T30, T32, T33, T34, T36, T37, T39 y T40), **todos validados** contra el temario oficial BOAM 10.032.

### Pendientes para QA / próxima iteración

- Validación de contenido por **María y Ana**, y de los ocho puntos abiertos por el **IAM** (ver `tema-35-validacion.md`), en especial **la frontera con el Tema 34**, que conviene fijar antes de generar ese tema.
- **Reverificar los datos volátiles antes de cada convocatoria.** Este tema es, junto con el T24 y el T31, el más sensible a la obsolescencia de la serie: adopción de IPv6 y de HTTP/3, calendario de duración de los certificados, publicación como RFC del intercambio híbrido post-cuántico **X25519MLKEM768** (pendiente en agosto de 2026), cifras de la UIT y de Red.es, art. 45 de eIDAS 2 y transposición de NIS2.
- Decidir si el criterio de **traducción de los términos ingleses** (punto 7 de la validación) se aplica de forma uniforme a toda la serie.
