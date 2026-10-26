# Informe de revisión (segunda ronda) — "Modelo Critic-EmpRAG1.0, Autorreflexión y Generación Aumentada por Recuperación (RAG) aplicadas a modelos de lenguaje pequeños para bases de conocimiento empresarial"

**Autor:** M.Sc. Alcides Yohacin Leaños Rodriguez · **Programa:** Doctorado en Ciencias de la Computación, UAGRM School of Engineering · **Versión revisada:** `PerfilLatexDocument/`, PDF de 43 páginas · **Fecha de revisión:** 23 de septiembre de 2026

> **Nota sobre la numeración.** Este informe conserva los identificadores del informe anterior para las observaciones que siguen abiertas, de modo que puedan rastrearse entre ambas rondas. Las observaciones nuevas —introducidas por las propias correcciones— se numeran con el prefijo **N**.

## Resumen ejecutivo

El documento revisado sigue siendo un **perfil de tesis**, de modo que no se evalúan diagnóstico ejecutado, propuesta desarrollada, resultados ni conclusiones.

El avance entre rondas es sustantivo y verificado: **las cuatro observaciones críticas están cerradas**. La cadena de coherencia troncal, que en la primera revisión se rompía en el paso de la hipótesis al diseño de validación, hoy se sostiene de punta a punta salvo en el eslabón de la hipótesis. El documento ya puede atribuir el efecto al mecanismo que postula, su variable dependiente está íntegramente operacionalizada y su aparato bibliográfico resiste verificación.

El hallazgo principal de esta ronda es de otra naturaleza: **cuatro de las once observaciones mayores son nuevas, y las cuatro fueron introducidas por las correcciones mismas**. Tres son contradicciones entre una sección corregida y otra que quedó sin actualizar; la cuarta es un indicador que referencia un contenido que el documento no define. Ninguna es grave por separado, pero en conjunto revelan que las correcciones se aplicaron puntualmente sin propagarse a las secciones que dependían de ellas.

**Veredicto: el perfil ya no tiene impedimentos de fondo para presentarse, pero no está listo para tribunal.** Debe resolver las cuatro contradicciones nuevas —trabajo de una sesión corta— y el bloque de hipótesis, que es lo único del tramo troncal que sigue abierto.

**Conteo: 0 críticas, 11 mayores, 4 menores.** (Ronda anterior: 4 críticas, 13 mayores, 6 menores.)

---

## Observaciones críticas

Ninguna. Las cuatro de la ronda anterior se verificaron cerradas:

| | Estado | Verificación |
|---|---|---|
| **C-01** — el diseño no aislaba el efecto del crítico híbrido | Cerrada | El Capítulo 2 declara dos niveles de validación empírica con unidades de análisis distintas, y la Tabla 2 especifica seis configuraciones cuyos contrastes descomponen el efecto. El par $C_3$–$C_4$ aísla el aporte del crítico híbrido; la ablación $C_{4b}$ lo verifica por supresión. |
| **C-02** — la operacionalización no cerraba | Cerrada con reserva | Las tres dimensiones de la Tabla 1 coinciden literalmente con la definición conceptual. La dimensión de productividad pasó de cero a cuatro indicadores, todos medibles en $A_0$ y $A_1$. La privacidad pasó de cero a dos. Reserva: ver M-14. |
| **C-03** — variables con tres definiciones distintas | Cerrada | Las cuatro ubicaciones que nombran las variables concuerdan. La formulación "confiabilidad de las respuestas" se conserva como concepto del marco teórico, sin etiqueta de variable. |
| **C-04** — referencia inexistente | Cerrada | Sustituida por una fuente con DOI resoluble, y la afirmación reescrita para ajustarse a lo que esa fuente demuestra. |

---

## Observaciones mayores

### [N-01] El capítulo se contradice sobre el tratamiento estadístico

- **Ubicación:** Capítulo 2, §2.1 Perspectiva epistemológica (línea 11) frente a §2.10 Análisis de los datos.

- **Evidencia:** En la perspectiva epistemológica:
  > "la validación práctica de la propuesta se realiza con herramientas cuantitativas de la **estadística paramétrica**, contrastando dos contextos $A_0$ y $A_1$."

  En el análisis de los datos:
  > "El contraste se realiza mediante la prueba $t$ de Student para muestras relacionadas, previa verificación del supuesto de normalidad […]; **de no satisfacerse dicho supuesto se aplica la prueba de Wilcoxon de rangos con signo**."

- **Problema:** La prueba de Wilcoxon y la de Friedman, ambas previstas en §2.10, son no paramétricas. El documento compromete en un epígrafe un enfoque que en otro declara condicional. La pauta de validación exige el estadístico apropiado aplicado a los datos, y no admite que el propio documento anuncie dos criterios incompatibles. Un examinador que lea el capítulo en orden encontrará la contradicción a diez páginas de distancia.

  Esta observación es consecuencia directa de la corrección anterior: el tratamiento estadístico se precisó en §2.10 y la mención de §2.1 quedó sin actualizar.

- **Corrección:** En §2.1, sustituir "estadística paramétrica" por una formulación neutra —"herramientas cuantitativas de la estadística inferencial"— y remitir a §2.10. En el mismo pasaje, la frase "Esta interacción da paso a un proceso pre experimental" debe recoger que la validación empírica comprende hoy dos componentes, no solo el preexperimento.

- **Confianza:** Verificado.

### [N-02] La delimitación espacial y las amenazas a la validez afirman lo contrario sobre la generalización

- **Ubicación:** Capítulo 2, §2.3 Delimitación espacial (línea 29) frente a §2.11 Amenazas a la validez, apartado de validez externa (línea 139).

- **Evidencia:** En la delimitación:
  > "los resultados y la arquitectura que se propone **son aplicables** en otras pequeñas y medianas empresas de desarrollo de *software* con similares restricciones."

  En las amenazas:
  > "su transferencia a otras organizaciones con restricciones equivalentes de privacidad e infraestructura **se plantea como hipótesis sujeta a validación posterior y no como resultado comprometido** por el presente estudio."

- **Problema:** El mismo capítulo afirma la aplicabilidad externa en indicativo y, once páginas después, la niega explícitamente. La contradicción es más visible que el problema original —que era solo una generalización excesiva— porque ahora el documento se desmiente a sí mismo. Es la observación M-08 de la ronda anterior, que la nueva sección de amenazas dejó a medio corregir.

- **Corrección:** Reformular la delimitación espacial en los términos de la sección de amenazas: la arquitectura *podría* transferirse a organizaciones con restricciones equivalentes, sujeto a validación posterior. Enunciar allí las condiciones de contorno (volumen de corpus, tipo de documentación, perfil del personal, restricciones de cómputo) y trasladar la afirmación fuerte a las líneas de continuidad. La misma afirmación aparece replicada en la justificación social y económica y debe ajustarse en ambos lugares.

- **Confianza:** Verificado.

### [N-03] La población y muestra no cubre la unidad de análisis del segundo nivel

- **Ubicación:** Capítulo 2, §2.9 Población y muestra, frente a §2.6 Niveles de la validación empírica y §2.10 Análisis de los datos.

- **Evidencia:** §2.9 declara únicamente:
  > "La población y muestra coinciden al 100 %, corresponde al personal de las áreas de TI y desarrollo de Dualbiz SRL. […] para un total de 18 personas."

  Pero §2.6 establece que el segundo nivel tiene otra unidad de análisis:
  > "Su unidad de análisis es **la consulta del banco de evaluación**."

  Y §2.10 opera sobre ella estadísticamente:
  > "cada configuración de la Tabla 2 se evalúa sobre el mismo banco de consultas, de modo que las observaciones también resultan **pareadas por consulta**."

- **Problema:** La pauta del diseño metodológico exige declarar las unidades de análisis con justificación de tamaño y selección. El documento tiene hoy dos unidades de análisis y solo declara una. No se dice cuántas consultas componen el banco, con qué criterio se seleccionan, ni cómo se asegura su representatividad del proceso de soporte. Sin ese dato, la potencia estadística del segundo nivel —que es donde se juega la novedad científica— es indeterminable, y el análisis de varianza de medidas repetidas que §2.10 anuncia no puede dimensionarse.

  Es consecuencia directa de la incorporación del segundo nivel: la sección de población y muestra no se actualizó al aparecer la nueva unidad.

- **Corrección:** Ampliar §2.9 para declarar ambas unidades de análisis. Para el segundo nivel: número previsto de consultas del banco, criterio de selección (por ejemplo, muestreo estratificado sobre las categorías del histórico de soporte), proporción de consultas sin respaldo documental incluidas deliberadamente, y justificación de que ese número permite detectar las diferencias esperadas entre configuraciones.

- **Confianza:** Verificado.

### [N-04] Un indicador remite a un contenido que el documento no define

- **Ubicación:** Tabla 1, indicador 2.3.4.

- **Evidencia:** El indicador reza:
  > "2.3.4. Superficies de exposición con control implementado, **sobre el total identificado**."

  La expresión "superficies de exposición" no aparece en ninguna otra parte del documento. No existe apartado, lista ni criterio que identifique cuáles son.

- **Problema:** Un indicador cuyo denominador remite a un conjunto que el documento nunca enumera no es calculable. La pauta exige que toda variable esté operacionalizada hasta el indicador y su instrumento; aquí el indicador existe pero es inaplicable tal como está redactado. Se introdujo al incorporar los indicadores de privacidad, sin el apartado que debía sustentarlos.

- **Corrección:** Incorporar en la delimitación temática, o en un apartado propio, el inventario de superficies de exposición del despliegue local: índice vectorial y representaciones densas, registros de consulta, respaldos, credenciales de acceso y política de retención. Ese inventario es además la corrección que M-11 requiere, de modo que ambas observaciones se resuelven con una misma acción.

- **Confianza:** Verificado.

### [M-01] La hipótesis sigue agregada, sin Hi/Ho/Ha, y ahora contradice el diseño de validación

- **Ubicación:** `6_FormulacionConstruccionTeor.tex:5`; §2.10 Análisis de los datos.

- **Evidencia:** La hipótesis es una proposición única:
  > "La implentación del Modelo crítico Critic-EmpRAG1.0 […] mejora la productividad y el acceso al Sistema de soporte de conocimiento empresarial interno de las áreas de TI y desarrollo en Dualbiz SRL."

  El documento no contiene ninguna formulación Hi / Ho / Ha (verificado: cero ocurrencias). Y §2.10 cierra:
  > "A partir de los datos obtenidos en **ambos niveles** se valida o no la hipótesis de investigación."

- **Problema:** La pauta de hipótesis fija el formato Hi / Ho / Ha y exige declarar el tipo según el alcance; para un alcance explicativo con variable independiente manipulada corresponde una hipótesis causal, que no se declara.

  La corrección del diseño agravó el problema en lugar de aliviarlo. Ahora hay dos niveles de validación que pueden arrojar resultados divergentes —la productividad organizacional puede mejorar mientras $C_4$ no supera a $C_3$— y una sola hipótesis que no dice qué hacer en ese caso. Tal como está redactado, §2.10 promete una decisión que el propio diseño no permite tomar de forma unívoca.

- **Corrección:** Desdoblar en dos hipótesis con sus respectivas Ho y Ha, alineadas con los dos niveles. La computacional debe enunciarse de modo falsable en términos de las configuraciones ("el anclaje del crítico en la evidencia recuperada produce una mejora en fundamentación superior a la del mismo sistema con crítico paramétrico"); la organizacional, en términos de los indicadores 2.2.1 a 2.2.4, que ya existen. Ajustar la frase final de §2.10 en consecuencia.

- **Confianza:** Verificado.

### [M-02] La validación no designa hipótesis de validación ni declara las fases del proceso experimental

- **Ubicación:** Capítulo 2, §2.6 y §2.10.
- **Evidencia:** No hay hipótesis de validación diferenciada de la de investigación, ni las fases de definición de alcance, planificación, operación, y análisis e interpretación. Verificado por búsqueda: cero ocurrencias.
- **Problema:** La pauta de validación exige ambas cosas de manera explícita. El documento ha ganado mucha precisión en el *qué* se compara y con *qué* estadístico, pero sigue sin declarar la secuencia del proceso experimental.
- **Corrección:** Añadir un apartado de validación que designe la hipótesis de validación y estructure las cuatro fases, indicando para cada una qué se hace, con qué instrumento y en qué hito del cronograma. Se resuelve en la misma acción que M-01.
- **Confianza:** Verificado.

### [M-06] El banco de evaluación sigue fuera de la lista de instrumentos, y el documento ya depende de él

- **Ubicación:** §2.8 Instrumentos de investigación.
- **Evidencia:** La lista contiene cinco instrumentos y ninguno es el banco de evaluación. Sin embargo, el documento lo invoca en cinco pasajes: el epígrafe de los niveles de validación, el análisis de los datos, dos apartados de amenazas a la validez, la nota al pie de la Tabla 1 y el aporte práctico.
- **Problema:** La regla de coherencia metodológica establece que cada método debe tener su técnica y su instrumento, y que ese instrumento se use efectivamente. El banco de evaluación es el instrumento del segundo nivel completo y es el único que no está declarado. La observación se agrava respecto de la ronda anterior: entonces era una omisión, ahora es el sostén de la mitad de la validación empírica. La nota de la Tabla 1 remite explícitamente a un instrumento que la sección de instrumentos no reconoce.
- **Corrección:** Incorporarlo a §2.8 y especificarlo: composición, criterio de selección de consultas, procedimiento de construcción de las respuestas esperadas y de la evidencia documental de referencia, perfil de quien las elabora y de quien las revisa, y tratamiento de la confidencialidad. Se resuelve junto con N-03, que pide el mismo dato desde la sección de población y muestra.
- **Confianza:** Verificado.

### [M-14] Dos indicadores de la Tabla 1 carecen de protocolo de medición

- **Ubicación:** Tabla 1, indicadores 2.1.2 y 2.1.4; §2.5 Definición operacional de las variables.
- **Evidencia:** El indicador 2.1.2 define la tasa de alucinación como "afirmaciones no sustentadas por la evidencia recuperada, sobre el total de afirmaciones verificables", y el 2.1.4 como "puntaje de fidelidad respecto a los documentos recuperados". §2.5 consta de una sola oración que remite a la tabla, sin describir ningún procedimiento.
- **Problema:** Ambos indicadores exigen un juicio sobre si una afirmación está o no sustentada, y el documento no dice quién lo emite ni bajo qué criterio. Sin unidad de análisis declarada (la afirmación, la oración o la respuesta completa), sin protocolo de anotación y sin medida de acuerdo entre anotadores, los valores resultantes no son reproducibles ni auditables. Es el cierre pendiente de la reconstrucción de la Tabla 1.
- **Corrección:** Desarrollar §2.5 con el protocolo: unidad de anotación, criterio de sustentación, número y perfil de los anotadores, porcentaje de la muestra sometido a doble anotación y estadístico de acuerdo (kappa de Cohen o equivalente) con su umbral de aceptación.
- **Confianza:** Verificado.

### [M-03] Los antecedentes no siguen el orden exigido ni incluyen representación gráfica de la situación problemática

- **Ubicación:** `1_Antecedentes.tex` completo.
- **Evidencia:** La sección abre con el estado del arte de RAG y llega a la situación de Dualbiz SRL en el cuarto párrafo. Ninguna investigación se expone con su problema, su propuesta y su resultado. Búsqueda de FODA, Ishikawa o árbol de problemas: cero ocurrencias.
- **Problema:** La pauta de antecedentes fija el orden —situación problemática, importancia, mínimo tres investigaciones con problema/propuesta/resultado, vacío del conocimiento, y situación representada con FODA, Ishikawa o árbol de problemas— y el documento incumple los puntos 1, 3 y 5. El punto 4, el vacío del conocimiento, está bien resuelto y mejoró en esta ronda al corregirse el conector lógico.
- **Corrección:** Reordenar conforme a la pauta; reescribir al menos tres antecedentes en formato problema–propuesta–resultado (se sugieren Self-RAG, Self-BioRAG y CRAG); e incorporar un árbol de problemas de la situación en Dualbiz SRL.
- **Confianza:** Verificado.

### [M-04] El perfil sigue sin contener ningún diagrama

- **Ubicación:** Documento completo, 43 páginas.
- **Evidencia:** Cero entornos `figure` y cero `includegraphics` en el cuerpo. Las tres figuras numeradas son tablas.
- **Problema:** La pauta de propuesta exige mostrar gráficamente, por diagrama, cómo será la solución. La observación se agudiza en esta ronda: el documento ahora describe seis configuraciones que difieren en un componente cada una, y esa arquitectura comparativa se sostiene íntegramente en prosa. Un diagrama de $C_1$ a $C_4$ haría evidente en un vistazo lo que hoy exige leer dos páginas.
- **Corrección:** Incorporar un diagrama de arquitectura de Critic-EmpRAG1.0 —recuperador, crítico híbrido, generador, punto de acceso del crítico a la evidencia recuperada, ciclos correctivos— y, si el espacio lo permite, un segundo diagrama que superponga las configuraciones de la Tabla 2.
- **Confianza:** Verificado.

### [M-10] El protocolo Delphi sigue incompleto

- **Ubicación:** §2.6, "Consulta a expertos (método Delphi)".
- **Evidencia:** Se define la selección por coeficiente de competencia y dos perfiles de especialistas. Búsqueda de "rondas", "consenso" o "Kendall": cero ocurrencias.
- **Problema:** Sin número de expertos, número de rondas, criterio de consenso, medida de estabilidad entre rondas ni condición de cierre, el resultado del Delphi no es interpretable ni auditable, y la validación teórica del cuarto objetivo específico queda sin procedimiento verificable. El contraste con el nivel de detalle que hoy tiene la validación empírica es notorio.
- **Corrección:** Declarar número previsto de expertos por perfil, umbral del coeficiente de competencia, número de rondas, estadístico de consenso con su umbral y condición de cierre.
- **Confianza:** Verificado.

### [M-11] La privacidad se argumenta por ausencia de terceros, sin modelo de amenazas

- **Ubicación:** §2.3 Delimitación temática.
- **Evidencia:** > "se enmarcan en las políticas internas de confidencialidad de la información, **al no requerir el envío de información privada a servicios de terceros**."
- **Problema:** La no exposición a terceros es condición necesaria pero no suficiente: un despliegue local conserva superficies de riesgo propias. La observación avanzó parcialmente —la Tabla 1 incorporó los indicadores 2.3.3 y 2.3.4— pero el argumento del texto no cambió, y el indicador 2.3.4 quedó sin referente (N-04).
- **Corrección:** Incorporar el modelo de amenazas. Resuelve simultáneamente N-04.
- **Confianza:** Verificado.

### [M-05] El tratamiento estadístico quedó corregido solo parcialmente

Ver **N-01**, que documenta el pasaje no actualizado. Se consigna aquí para trazabilidad con el informe anterior.

---

## Observaciones menores

- **[m-01]** Erratas verificadas: "empresaial" (`0_Introduccion.tex:10`), "Sistema Sistemas" (`2_Problema.tex:11`), "indentificación" (`3_Objetivos.tex:13`), "en la la mejora" (`3_Objetivos.tex:17`), "implentación" y "especifico" (`6_FormulacionConstruccionTeor.tex:5`), "domínio" (`08_Capitulo02_ProyecMetodolo.tex:45`).
- **[m-02]** `0_Introduccion.tex:10`: oración subordinada sin oración principal; y "son entrenados sobre entornos de la nube" es conceptualmente impreciso.
- **[m-03]** `0_Introduccion.tex:8`: "mejor conocido en español como Generación Aumentada por Recuperación conocida" — duplicación.
- **[m-04]** `3_Objetivos.tex:5`: las comillas de `''Critic-EmpRAG1.0''` abren con el carácter de cierre.

Las observaciones menores m-05 y m-06 de la ronda anterior (la errata "Sel-RAG" y el nombre castellanizado "Reflexión") se verificaron corregidas.

---

## Hoja de ruta de correcciones

**Primera etapa — cerrar las contradicciones, en una sesión.** N-01, N-02 y N-04 son ediciones de uno o dos párrafos cada una, y no dependen de nada. Deben hacerse antes que el resto porque son el tipo de incoherencia que un tribunal detecta sin esfuerzo y que desmerece el trabajo de fondo ya realizado. N-04 se resuelve junto con M-11, ya que ambas piden el mismo inventario.

**Segunda etapa — cerrar el bloque de la validación.** N-03 y M-06 piden el mismo dato desde secciones distintas —la especificación del banco de evaluación— y deben redactarse de una sola vez. A continuación M-14, que completa los protocolos de medición, y después M-01 y M-02, que formulan las hipótesis y el proceso experimental sobre la base ya consolidada. Este bloque cierra el último eslabón abierto de la cadena troncal.

**Tercera etapa — las secciones que faltan.** M-03 (reestructurar antecedentes e incorporar el árbol de problemas) y M-04 (los diagramas). Son trabajo de redacción y representación, independientes entre sí y de lo anterior, pero se benefician de que el diseño ya esté fijado.

**Cuarta etapa — M-10** (protocolo Delphi) y las menores.

---

## Fortalezas

1. **La cadena troncal se sostiene hoy casi íntegra.** El problema porta objeto y campo; el objetivo general está construido con qué, cómo, para qué y dónde; hay exactamente cuatro objetivos específicos en el orden exigido; las variables están definidas de manera única y operacionalizadas hasta el indicador; y el diseño metodológico puede contrastar lo que la hipótesis afirma. El único eslabón que sigue abierto es la formulación de la hipótesis misma.

2. **La validación empírica pasó de declarativa a ejecutable.** El documento distingue dos niveles con sus unidades de análisis, especifica seis configuraciones cuyos contrastes descomponen el efecto, y nombra las pruebas estadísticas con sus supuestos y alternativas. Es un salto de calidad considerable respecto de la ronda anterior, y sitúa el trabajo por encima de lo habitual en un perfil.

3. **La sección de amenazas a la validez está bien construida y es honesta.** Trata las cuatro categorías, apoya la de constructo en literatura de ingeniería pertinente, y declara sin rodeos la limitación derivada de que la validación de un sistema RAG solo sea plenamente factible en operación. Declarar esa tensión en lugar de ocultarla fortalece la posición del autor ante el tribunal. Reconoce además el conflicto de rol del investigador y propone una mitigación concreta.

4. **El aparato bibliográfico resiste verificación.** Sin referencias inexistentes, con identificadores digitales comprobados contra registro y sin citas escritas a mano fuera del sistema de citación. Para un trabajo cuya novedad se apoya en el posicionamiento frente a dos antecedentes precisos, esa solidez no es un detalle de forma.
