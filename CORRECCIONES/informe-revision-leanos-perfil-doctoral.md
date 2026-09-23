# Informe de revisión — "Modelo Critic-EmpRAG1.0, Autorreflexión y Generación Aumentada por Recuperación (RAG) aplicadas a modelos de lenguaje pequeños para bases de conocimiento empresarial"

**Autor:** M.Sc. Alcides Yohacin Leaños Rodriguez · **Programa:** Doctorado en Ciencias de la Computación, UAGRM School of Engineering · **Versión revisada:** `PerfilLatexDocument/` (PDF compilado, 38 páginas) · **Fecha de revisión:** 22 de septiembre de 2026

---

## Resumen ejecutivo

El documento revisado es un **perfil de tesis**, no una tesis completa. En consecuencia no se evalúan diagnóstico ejecutado, propuesta desarrollada, resultados, análisis estadístico real ni conclusiones: esas secciones no existen todavía y su ausencia no constituye observación. Sí se evalúan la cadena de coherencia troncal, la conformidad de las secciones presentes, el diseño metodológico proyectado, la operacionalización de variables y la consistencia de artefactos y referencias.

La cadena troncal está **bien construida en su tramo superior** —problema, objeto, campo, objetivo general y los cuatro objetivos específicos cumplen las pautas con precisión poco común— y **se rompe en el tramo inferior**, en el paso de la hipótesis al diseño de validación. Cuatro observaciones críticas concentran ese quiebre: el diseño no puede atribuir el efecto al mecanismo que constituye la novedad científica; la tabla de operacionalización no cierra ni con la definición conceptual de la variable dependiente ni con el diseño preexperimental declarado; las variables están definidas de forma distinta en tres lugares del documento; y una referencia que sostiene una dimensión central de la variable dependiente no existe.

**Veredicto: el perfil no está listo para defensa ante tribunal.** Requiere resolver las 4 observaciones críticas y, como mínimo, las observaciones mayores M-01 a M-05 antes de presentarse. El trabajo tiene base conceptual sólida y una novedad científica genuinamente defendible; el problema no es el aporte, es que el diseño actual no puede demostrarlo.

**Conteo: 4 críticas, 13 mayores, 6 menores.**

---

## Observaciones críticas

### [C-01] El diseño A₀→A₁ no puede atribuir la mejora al crítico híbrido, que es la novedad científica declarada

- **Ubicación:** Capítulo 2, "Métodos del nivel empírico" (`08_Capitulo02_ProyecMetodolo.tex:100`); novedad científica en `6_FormulacionConstruccionTeor.tex:40`.

- **Evidencia:**
  > "Se interviene deliberadamente introduciendo el modelo crítico en el acceso al Sistema de soporte de conocimiento empresarial interno […] y se observa el efecto que dicha intervención produce (preprueba y posprueba con un solo grupo), contrastando el contexto inicial $A_0$, previo a la aplicación del modelo, con el contexto final $A_1$, posterior a su aplicación."

  Contrastado con la novedad declarada:
  > "La novedad científica de la investigación radica en dotar de especificidad de dominio al componente crítico […] mediante un crítico híbrido que ancla su juicio en la evidencia recuperada del corpus empresarial en lugar de hacerlo en parámetros ajustados con anotaciones de un modelo propietario."

- **Problema:** La pauta de hipótesis admite el preexperimento como diseño válido, y para una pregunta de transformación organizacional lo es. Pero la novedad científica que este perfil reclama no es organizacional: es la afirmación de que **trasladar la especificidad de dominio del plano paramétrico al no paramétrico** produce un crítico eficaz. Entre A₀ (proceso manual actual) y A₁ (prototipo desplegado) cambian simultáneamente al menos cinco cosas: la existencia de un sistema automatizado, el modelo de lenguaje, el mecanismo de recuperación, el componente crítico y el número de ciclos de inferencia. Cualquier mejora observada es atribuible a ese conjunto, no al crítico híbrido. Un tribunal doctoral preguntará —y la pregunta no tiene respuesta en el documento actual— cómo se sabe que el efecto no proviene simplemente de haber introducido un RAG convencional.

  Esta observación conecta además con la pauta de amenazas a la validez: la validez de constructo del estudio depende enteramente de poder aislar el mecanismo, y no se discute en ninguna parte del perfil.

- **Corrección:** Separar explícitamente dos niveles de validación, y declararlos como tales en el diseño metodológico:

  1. **Validación científica (computacional).** Incorporar un diseño ablativo sobre el banco de evaluación, con configuraciones que permitan descomponer el efecto: SLM sin RAG (línea base generativa); SLM + RAG convencional (aporte de la recuperación); SLM + RAG + crítica puramente paramétrica (aporte de la autorreflexión convencional); SLM + RAG + Critic-EmpRAG1.0 (sistema completo); Critic-EmpRAG1.0 sin ciclo correctivo (ablación del refinamiento); Critic-EmpRAG1.0 sin evidencia externa para el crítico (ablación del componente no paramétrico, que es la ablación decisiva: aísla exactamente lo que el perfil reclama como novedad).
  2. **Validación organizacional.** Conservar el preexperimento A₀→A₁ con los 18 participantes, reformulado para responder la pregunta de transformación del campo de acción.

  Esto no obliga a reescribir el objetivo general ni los objetivos específicos: OE4 dice "Validar teórica y empíricamente", y ambos niveles caben bajo esa formulación. Sí obliga a desdoblar la hipótesis (ver M-01) y a ampliar el diseño metodológico.

- **Confianza:** Verificado.

---

### [C-02] La tabla de operacionalización no cierra ni con la definición conceptual de la variable dependiente ni con el diseño preexperimental

- **Ubicación:** Definición conceptual en `08_Capitulo02_ProyecMetodolo.tex:88-92`; Tabla 1, "Operacionalización de las variables" (`_tablasyCuadros/Cuadro1_OperacionalizacionVariables.tex:22-36`).

- **Evidencia:** La definición conceptual descompone la variable dependiente en tres dimensiones:

  > "**Fundamentación y confiabilidad.** […] **Productividad del proceso de consulta.** Efecto del sistema sobre el desempeño del proceso real de consulta al conocimiento operativo, expresado en el tiempo necesario para resolver una consulta y en la autonomía del personal frente a la dependencia de supervisión experimentada. […] **Viabilidad bajo restricciones.** Grado en que el sistema opera dentro de los límites de infraestructura de cómputo disponibles **y sin exponer conocimiento confidencial a servicios de terceros**."

  La Tabla 1 declara en cambio: 2.1 Precisión y exactitud (accuracy/F1, tasa de alucinación); 2.2 Fundamentación (proporción de afirmaciones con fuente, faithfulness); 2.3 Eficiencia computacional (latencia, memoria/GPU).

  Cruzando ambas listas:

  | Dimensión conceptual | Indicadores en la Tabla 1 |
  |---|---|
  | Fundamentación y confiabilidad | 2.1 y 2.2 |
  | **Productividad del proceso de consulta** (tiempo, autonomía) | **ninguno** |
  | Viabilidad bajo restricciones — cómputo | 2.3 |
  | Viabilidad bajo restricciones — **privacidad** | **ninguno** |

- **Problema:** Este desajuste tiene dos consecuencias independientes, ambas graves.

  **Primera: la hipótesis no es contrastable tal como está redactada.** La hipótesis afirma que el modelo "mejora **la productividad** y el acceso al Sistema de soporte de conocimiento empresarial interno". Sin indicadores de productividad, la mitad del enunciado no puede verificarse ni refutarse con ningún dato que el propio estudio prevea recolectar. La pauta de hipótesis exige que las variables y su relación sean "observables y medibles, con referentes en la realidad"; y la cadena troncal exige que las variables de la hipótesis estén operacionalizadas. Aquí no lo están. Lo mismo vale para la privacidad, que no es un detalle: es una de las dos restricciones que, según la novedad científica, hacen inaplicables Self-RAG y Self-BioRAG al contexto estudiado.

  **Segunda: los indicadores que sí existen no son aplicables en A₀.** La pauta de hipótesis define el preexperimento como aquel en que "se mide el antes (pre-test) y el después (post-test) de **las mismas variables o indicadores**; el instrumento de evaluación es **el mismo en ambos momentos**". El contexto A₀ es el proceso manual actual, previo a la introducción del sistema. En A₀ no existe recuperación de documentos, de modo que el indicador 2.2.2 (*puntaje de fidelidad respecto a los documentos recuperados*) carece de referente; y no existe inferencia sobre GPU, de modo que el indicador 2.3.2 (*consumo de recursos de cómputo, memoria/GPU*) tampoco lo tiene. Con la Tabla 1 actual **la preprueba no tiene sobre qué aplicarse**, y el preexperimento declarado es inejecutable.

  Obsérvese la simetría del problema: la encuesta prevista en las técnicas sí mide A₀ —"para obtener datos cuantificables sobre el tiempo y la efectividad del proceso actual de consulta"— pero mide justamente la dimensión que la tabla no operacionaliza. El instrumento existe para la dimensión sin indicadores, y los indicadores existen para lo que el instrumento no mide.

- **Corrección:** Reconstruir la Tabla 1 de modo que las tres dimensiones conceptuales tengan indicadores, distinguiendo explícitamente cuáles se miden en ambos contextos y cuáles solo en A₁:

  - **Productividad del proceso de consulta** (medible en A₀ y A₁, mismo instrumento): tiempo medio para resolver una consulta operativa; tasa de consultas resueltas sin escalamiento a personal experimentado (autonomía); número de interrupciones a personal senior por semana; esfuerzo percibido en escala Likert.
  - **Privacidad** (medible en A₁, verificable por auditoría): proporción de consultas resueltas sin salida de datos hacia servicios de terceros; inventario de superficies de exposición (índice vectorial, *embeddings*, registros de consulta, respaldos); política de retención y control de accesos.
  - **Indicadores de sistema** (accuracy/F1, alucinación, faithfulness, latencia, GPU): reclasificarlos explícitamente como métricas del **experimento ablativo** de C-01, no del contraste A₀→A₁, y definir para ellos el banco de evaluación (ver M-06) y los protocolos de anotación (ver M-07).

  La nota al pie de la tabla —"La identificación de las dimensiones e indicadores es perfectible bajo este estudio"— no sustituye esta corrección ante un tribunal; conviene retirarla una vez cerrada la operacionalización.

- **Confianza:** Verificado.

---

### [C-03] Las variables de investigación están definidas de forma distinta en tres lugares del documento

- **Ubicación:** `6_FormulacionConstruccionTeor.tex:9-11`; `7_Capitulo01ProspeccionMArcoTeorico.tex:27-28`; `08_Capitulo02_ProyecMetodolo.tex:22`.

- **Evidencia:** En la sección de identificación de variables:
  > "**Variable independiente**: Modelo crítico Critic-EmpRAG1.0. **Variable dependiente**: Productividad y acceso al conocimiento."

  En los referentes conceptuales del Capítulo 1:
  > "**Arquitectura de autorreflexión sobre RAG (Variable independiente):** conjunto de mecanismos mediante los cuales un agente evalúa la evidencia recuperada […] **Confiabilidad de las respuestas (Variable dependiente):** grado de fundamentación y ausencia de alucinación de las respuestas generadas sobre conocimiento empresarial interno."

  Y en el enfoque y diseño del Capítulo 2:
  > "esta se llevará a la práctica mediante un prototipo para verificar la transformación en **la confiabilidad de las respuestas** sobre conocimiento empresarial interno como meta de la investigación."

- **Problema:** La cadena de coherencia troncal exige que las variables salgan del objeto y el campo y se mantengan idénticas desde la hipótesis hasta la validación. Aquí la variable independiente aparece como "Modelo crítico Critic-EmpRAG1.0" y como "Arquitectura de autorreflexión sobre RAG"; la dependiente, como "Productividad y acceso al conocimiento" y como "Confiabilidad de las respuestas". No son sinónimos: la confiabilidad es **una de las tres dimensiones** de la productividad y acceso según la propia definición conceptual del Capítulo 2. Un lector riguroso concluirá que el documento no ha decidido qué mide, y un miembro de tribunal que lea los capítulos en orden encontrará la meta de la investigación enunciada de dos maneras incompatibles en páginas consecutivas.

  Esta observación agrava C-02: parte del faltante de indicadores de productividad se explica porque la Tabla 1 parece haber sido construida contra la definición antigua (confiabilidad de las respuestas), no contra la vigente.

- **Corrección:** Fijar una sola formulación de cada variable —la de la sección de identificación de variables, que es la que concuerda con la hipótesis, el objetivo general y el campo de acción— y propagarla a los referentes conceptuales del Capítulo 1 y al enfoque del Capítulo 2. En los referentes conceptuales, renombrar las dos entradas y conservar "confiabilidad de las respuestas" como concepto del marco teórico, sin la etiqueta "(Variable dependiente)".

- **Confianza:** Verificado.

---

### [C-04] Una referencia que sostiene la dimensión de productividad no existe

- **Ubicación:** `08_Capitulo02_ProyecMetodolo.tex:90`; entrada `Chen2024_Helpdesk` en `_bibliografia.bib`.

- **Evidencia:** En la definición conceptual de la dimensión "Productividad del proceso de consulta":
  > "Cuenta como referente el empleo de agentes con base en RAG para la automatización del soporte de tecnologías de la información (Chen et al., 2024)."

  Verificación de la entrada bibliográfica:
  - DOI declarado `10.1109/ACCESS.2024.1234567` → **HTTP 404** en Crossref. El sufijo `1234567` es un marcador de posición, no un identificador registrado.
  - Búsqueda del título completo ("RAG-Enhanced Intelligent Agents for IT Helpdesk Automation with Self-Correction") en Crossref → **cero coincidencias**.
  - Autores declarados: "Chen, Lei; Wang, Rui; Zhang, Yong; Liu, Hao" — cuatro combinaciones de los apellidos y nombres de pila más frecuentes.
  - Volumen 12 y páginas 45231–45248 de *IEEE Access* (2024) no verificables contra ningún registro.

- **Problema:** Una referencia inexistente en un perfil de tesis doctoral es un hallazgo de credibilidad, no de forma. Compromete la confianza del tribunal en el resto del aparato bibliográfico y puede dar lugar a cuestionamientos de integridad académica. El agravante aquí es la ubicación: es la **única** fuente que respalda la dimensión de productividad del proceso de consulta, que es precisamente la dimensión que C-02 identifica como no operacionalizada. Si un miembro de tribunal tira del hilo de "productividad", encontrará que no se mide y que su fundamento documental no existe.

- **Corrección:** Eliminar la entrada `Chen2024_Helpdesk` y la cláusula que la invoca, o sustituirla por una fuente real sobre agentes RAG en soporte de TI, verificada contra DOI resoluble. El párrafo se sostiene sin ella: la referencia a los procesos de inducción (Achury, 2016) que lo acompaña sí es verificable.

  Recomendación adicional del mismo orden: revisar la entrada `Jiang2024_KnowsWhat`, que combina el título y los autores de *How Can We Know What Language Models Know?* (Jiang Zhengbao et al., TACL vol. 8, 2020, DOI `10.1162/tacl_a_00324`) con un venue no correspondiente ("NAACL 2024") y un identificador arXiv (`2310.11512`) que pertenece a un artículo de teoría de cuerdas. Esa referencia sostiene el tercer marco teórico de la propuesta (calibración epistémica).

- **Confianza:** Verificado.

---

## Observaciones mayores

### [M-01] La hipótesis es una proposición agregada, sin Hi/Ho/Ha ni tipo declarado

- **Ubicación:** `6_FormulacionConstruccionTeor.tex:5`.
- **Evidencia:** > "La implentación del Modelo crítico Critic-EmpRAG1.0, incorporando mecanismos de autorreflexión en dominio especifico sobre una arquitectura RAG con modelos de lenguaje pequeños, mejora la productividad y el acceso al Sistema de soporte de conocimiento empresarial interno de las áreas de TI y desarrollo en Dualbiz SRL."
- **Problema:** Es la única hipótesis del documento y se enuncia como proposición suelta. La pauta de hipótesis exige el formato Hi / Ho / Ha y la declaración del tipo según el alcance; para un estudio explicativo con variable independiente manipulada corresponde una **hipótesis causal**, que no se declara como tal. Además, la hipótesis funde en un solo enunciado dos afirmaciones de naturaleza distinta —una computacional (el crítico híbrido mejora la fundamentación de las respuestas) y una organizacional (el sistema mejora la productividad del personal)— que se prueban con diseños, instrumentos y unidades de análisis diferentes. Mientras permanezcan fundidas, no es posible aceptar una y rechazar la otra.
- **Corrección:** Desdoblar en dos hipótesis con sus respectivas Ho y Ha, alineadas con los dos niveles de validación de C-01. La hipótesis computacional debe formularse de modo falsable en términos de las configuraciones ablativas ("el anclaje del crítico en evidencia recuperada produce una mejora en fundamentación superior a la del mismo sistema con crítico puramente paramétrico"); la organizacional, en términos de los indicadores de productividad que C-02 incorpora.
- **Confianza:** Verificado.

### [M-02] La validación no designa hipótesis de validación ni declara las fases del proceso experimental

- **Ubicación:** Capítulo 2, secciones "Métodos del nivel empírico" y "Análisis de los datos".
- **Evidencia:** El perfil declara el método preexperimental y el procesamiento estadístico, pero no contiene hipótesis de validación diferenciada de la hipótesis de investigación, ni las fases de definición de alcance, planificación, operación, y análisis e interpretación.
- **Problema:** La pauta de validación exige explícitamente que se designe una nueva hipótesis de validación y que se siga el proceso experimental en sus cuatro fases. Ninguna de las dos condiciones se cumple.
- **Corrección:** Añadir una subsección de validación que designe la hipótesis de validación y estructure las cuatro fases, indicando para cada una qué se hará, con qué instrumento y en qué momento del cronograma.
- **Confianza:** Verificado.

### [M-03] Los antecedentes no siguen el orden exigido, no presentan investigaciones con la tripleta problema–propuesta–resultado y carecen de representación gráfica de la situación problemática

- **Ubicación:** `1_Antecedentes.tex` completo.
- **Evidencia:** La sección abre con el estado del arte de RAG (párrafos 1 y 2) y llega a la situación problemática de Dualbiz SRL recién en el párrafo 4. Las investigaciones citadas (Lewis, Karpukhin, Guu, Shinn, Madaan, Yao, Zamfirescu, Schmucker, Jeong) se mencionan en prosa continua, sin que ninguna se exponga con su problema, su propuesta y su resultado. No hay FODA, Ishikawa ni árbol de problemas en la sección ni en el resto del documento.
- **Problema:** La pauta de antecedentes fija un orden de redacción —(1) situación problemática, (2) importancia y relevancia, (3) mínimo tres investigaciones cada una con problema, propuesta y resultado, (4) vacío del conocimiento, (5) situación problemática representada con FODA, Ishikawa o árbol de problemas— y el documento incumple los puntos 1, 3 y 5. El punto 4 sí se cumple y está bien logrado.
- **Corrección:** Reordenar la sección conforme a la pauta; reescribir al menos tres de los antecedentes (se sugiere Self-RAG, Self-BioRAG y CRAG, por ser los más próximos al objeto) en formato problema–propuesta–resultado; e incorporar un árbol de problemas de la situación en Dualbiz SRL, que es la técnica más adecuada de las tres para un problema de proceso.
- **Confianza:** Verificado.

### [M-04] El perfil no contiene ningún diagrama, en particular ninguno de la propuesta

- **Ubicación:** Documento completo (38 páginas).
- **Evidencia:** No existe ningún entorno `figure` ni `includegraphics` en el cuerpo del documento; la única imagen es el logotipo institucional de la carátula. El archivo `contenido/_images/img_smsProcess.tex` existe en el proyecto pero no se incluye en ninguna parte. Las únicas dos figuras numeradas son tablas (operacionalización y cronograma).
- **Problema:** La pauta de propuesta exige mostrar gráficamente, por diagrama, cómo será la solución. El Modelo crítico Critic-EmpRAG1.0 se nombra a lo largo de todo el documento y se describe en prosa, pero nunca se representa. Para un perfil doctoral cuyo aporte teórico central *es* un modelo —"entendido no como una implementación de software sino como una construcción teórica que establece los componentes, las relaciones entre ellos y las condiciones bajo las cuales…"— la ausencia de una representación de esos componentes y relaciones es una carencia que el tribunal notará de inmediato.
- **Corrección:** Incorporar al menos un diagrama de arquitectura de Critic-EmpRAG1.0 que muestre los tres componentes (recuperador, crítico híbrido, generador), el flujo de la consulta, el punto exacto donde el crítico accede a la evidencia recuperada —que es donde reside la novedad— y los ciclos correctivos. Un segundo diagrama que contraste la propuesta con Self-RAG y Self-BioRAG haría visible el aporte sin necesidad de argumentarlo en prosa.
- **Confianza:** Verificado.

### [M-05] "Estadística paramétrica" sin especificación, y n=18 sin justificación de suficiencia

- **Ubicación:** `08_Capitulo02_ProyecMetodolo.tex:104` y `:106`.
- **Evidencia:** > "La población y muestra coinciden al 100%, corresponde al personal de las áreas de TI y desarrollo de Dualbiz SRL. incluyendo al responsable de dichas áreas, para un total de 18 personas."
  > "Los datos cuantitativos obtenidos de la evaluación del prototipo en los contextos $A_0$ y $A_1$ se procesarán mediante estadística paramétrica, para verificar la transformación con la introducción del modelo."
- **Problema:** La pauta de diseño metodológico exige justificación del tamaño y la selección de la muestra, y la de validación exige el estadístico apropiado aplicado a los datos. Declarar "estadística paramétrica" compromete de antemano a un supuesto de normalidad que con n=18 y mediciones pareadas puede no sostenerse, sin nombrar la prueba concreta ni prever qué hacer si el supuesto falla. El censo de 18 personas es defendible como unidad de análisis organizacional, pero requiere decirlo explícitamente y acotar en consecuencia el alcance de la inferencia.
- **Corrección:** Nombrar la prueba prevista para el contraste pareado A₀–A₁ (t de Student para muestras relacionadas), declarar la prueba de normalidad que condicionará su uso (Shapiro-Wilk, apropiada para n pequeño) y la alternativa no paramétrica si el supuesto no se cumple (Wilcoxon de rangos con signo). Añadir tamaño del efecto e intervalos de confianza, no solo el valor p. Justificar el censo y declarar que el n disponible limita la potencia estadística, lo que debe reflejarse en M-07.
- **Confianza:** Verificado.

### [M-06] El banco de evaluación no figura entre los instrumentos del diseño metodológico

- **Ubicación:** Lista de instrumentos en `08_Capitulo02_ProyecMetodolo.tex`, contrastada con `6_FormulacionConstruccionTeor.tex:32`.
- **Evidencia:** La lista de instrumentos comprende guía de análisis documental, guía de entrevista, cuestionario de encuesta, cuestionario de consulta a expertos y guía de observación. El banco de evaluación aparece únicamente en el aporte práctico: > "**El banco de evaluación de conocimiento empresarial interno**, conformado por consultas representativas del proceso de soporte, sus respuestas esperadas y la evidencia documental de referencia que las sustenta […] y utilizable como instrumento de medición en los contextos $A_0$ y $A_1$."
- **Problema:** La regla de coherencia metodológica establece que cada método debe tener su técnica y su instrumento, y que ese instrumento debe usarse efectivamente. El método preexperimental es el método central de la validación empírica y es el único que no tiene instrumento declarado en la sección correspondiente. El instrumento existe —el propio documento lo describe— pero está en el capítulo equivocado. Además, tal como se describe, no está especificado: no se dice cuántas consultas lo componen, cómo se seleccionan, quién construye la verdad de referencia ni quién la revisa.
- **Corrección:** Trasladar el banco de evaluación a la lista de instrumentos y especificarlo: número y criterio de selección de las consultas, procedimiento de construcción de las respuestas esperadas y de la evidencia documental de referencia, perfil de quien las elabora y de quien las revisa, y tratamiento de la confidencialidad del contenido.
- **Confianza:** Verificado.

### [M-07] Las amenazas a la validez no se discuten en ninguna parte del perfil

- **Ubicación:** Capítulo 2 completo.
- **Evidencia:** No existe sección ni párrafo que trate la validez interna, externa, de constructo o de conclusión.
- **Problema:** Su ausencia es observación en sí misma. En este perfil las amenazas son además identificables y concretas: efecto de novedad sobre los participantes, ausencia de grupo de control, tamaño muestral, dependencia de un único caso, y —la más seria— el hecho de que el investigador es simultáneamente quien diseña el modelo, construye el banco de evaluación y mide los resultados.
- **Corrección:** Añadir una subsección de amenazas a la validez con las cuatro categorías y, para cada amenaza, la medida de mitigación prevista. Para el conflicto de rol del investigador, considerar anotación independiente del banco de evaluación o doble evaluación ciega de un subconjunto.
- **Confianza:** Verificado.

### [M-08] La generalización a otras PyME excede lo que el diseño puede sostener

- **Ubicación:** Delimitación espacial, `08_Capitulo02_ProyecMetodolo.tex:29`; reiterada en la justificación social y económica.
- **Evidencia:** > "Si bien el estudio se realiza y valida sobre el conocimiento operativo específico de dicha organización, los resultados y la arquitectura que se propone **son aplicables** en otras pequeñas y medianas empresas de desarrollo de *software* con similares restricciones de privacidad de datos e infraestructura de cómputo."
- **Problema:** Se afirma aplicabilidad externa en indicativo, a partir de un caso único con n=18 y sin ninguna validación fuera de Dualbiz SRL. La afirmación no es demostrable dentro del alcance declarado.
- **Corrección:** Reformular como transferibilidad hipotética sujeta a validación posterior, y enunciar las condiciones de contorno bajo las cuales sería razonable esperar transferencia (volumen de corpus, tipo de documentación, perfil del personal, restricciones de hardware). Trasladar la afirmación fuerte a las líneas de continuidad.
- **Confianza:** Verificado.

### [M-09] Confusión entre alcance y diseño: "alcance pre experimental"

- **Ubicación:** `08_Capitulo02_ProyecMetodolo.tex:22`.
- **Evidencia:** > "Con un alcance pre experimental, se contrastará el acceso al Sistema de conocimiento en el contexto inicial $A_0$ y final $A_1$."
- **Problema:** La pauta de diseño metodológico define el alcance como exploratorio, descriptivo, correlacional o explicativo. "Preexperimental" no es un alcance sino un diseño. Dado que se manipula la variable independiente y se busca relación causa–efecto, el alcance corresponde a **explicativo**, con diseño preexperimental.
- **Corrección:** Redactar "alcance explicativo, con diseño preexperimental de preprueba y posprueba con un solo grupo". Verificar coherencia con el tipo de hipótesis que M-01 introduce (causal).
- **Confianza:** Verificado.

### [M-10] El protocolo Delphi está incompleto

- **Ubicación:** `08_Capitulo02_ProyecMetodolo.tex`, "Consulta a expertos (método Delphi)".
- **Evidencia:** Se define la selección por coeficiente de competencia y dos perfiles de especialistas, pero no el número de expertos, el número de rondas, el criterio de consenso, la medida de estabilidad entre rondas ni la condición de cierre.
- **Problema:** Sin criterio de consenso y condición de cierre declarados, el resultado del Delphi no es interpretable ni auditable, y la validación teórica del OE4 queda sin procedimiento verificable.
- **Corrección:** Declarar número previsto de expertos por perfil, número de rondas, umbral del coeficiente de competencia para la inclusión, estadístico de consenso (coeficiente de concordancia de Kendall o equivalente) con su umbral, y la condición de cierre. La base existente —coeficiente de competencia y dos perfiles complementarios— es correcta y sirve de punto de partida.
- **Confianza:** Verificado.

### [M-11] La privacidad se argumenta por ausencia de terceros, sin modelo de amenazas

- **Ubicación:** Delimitación temática, `08_Capitulo02_ProyecMetodolo.tex:25`.
- **Evidencia:** > "el diseño del prototipo y el tratamiento del conocimiento operativo de Dualbiz SRL se enmarcan en las políticas internas de confidencialidad de la información, **al no requerir el envío de información privada a servicios de terceros**."
- **Problema:** La no exposición a terceros es condición necesaria pero no suficiente. Un despliegue *on-premise* mantiene superficies de riesgo propias: el índice vectorial y los *embeddings* (de los que es posible reconstruir texto parcialmente), los registros de consultas, los respaldos, los permisos de acceso diferenciados por rol y la retención de datos. Dado que la privacidad es uno de los dos pilares de la novedad científica —es la razón por la que Self-BioRAG se declara inaplicable— el argumento actual es más débil de lo que la tesis necesita.
- **Corrección:** Incorporar un modelo de amenazas breve que enumere los activos, las superficies de exposición del despliegue local, los controles previstos (segmentación de accesos por rol, política de retención de logs, cifrado en reposo del índice) y el procedimiento de anonimización del banco de evaluación. Esto además provee los indicadores de privacidad que C-02 requiere.
- **Confianza:** Verificado.

### [M-12] Citas fuera del sistema bibliográfico en la justificación teórica

- **Ubicación:** `4_Justificacion+Alcance.tex:6`.
- **Evidencia:** > "Si bien **Asai et al. (2024)** con su herramienta Self-RAG […] **Jeong et al. (2024)** (publicado en Bioinformatics, ISMB 2024) se enfoca puntualmente sobre Dominios específicos en Biomedicina."
  Ambas citas están escritas manualmente como texto plano, no mediante el sistema de citación; las mismas fuentes sí se citan correctamente en otras secciones.
- **Problema:** La pauta de marco teórico exige que referencias, citas y paráfrasis estén siempre en formato APA 7 gestionado consistentemente. Las citas manuales no quedan vinculadas a la lista de referencias, no se actualizan si cambia la entrada y son la vía habitual por la que aparecen discrepancias de año o de autoría entre el texto y la bibliografía.
- **Corrección:** Sustituirlas por las macros de citación correspondientes a `Asai2024_Selfrag` y `jeong_improving_2024`.
- **Confianza:** Verificado.

### [M-13] Conector lógico erróneo en el enunciado del vacío de conocimiento

- **Ubicación:** `1_Antecedentes.tex:12`.
- **Evidencia:** > "existe evidencia teórica consolidada de que RAG y la autorreflexión a partir de la implementación de modelos críticos en combinación mejoran la confiabilidad de los modelos de lenguaje. **En consecuencia** no existe una arquitectura validada que integre ambos mecanismos."
- **Problema:** "En consecuencia" establece una relación causal entre la existencia de evidencia consolidada y la inexistencia de una arquitectura validada, lo cual es un contrasentido. El conector requerido es adversativo. La frase se encuentra en el enunciado del vacío de conocimiento, es decir, en el punto exacto donde se justifica la pertinencia de toda la investigación doctoral: tal como está redactada, el argumento central se lee como un error de razonamiento.
- **Corrección:** Sustituir por "Sin embargo" o "No obstante".
- **Confianza:** Verificado.

---

## Observaciones menores

- **[m-01]** Erratas: "implentación" y "especifico" (`6_FormulacionConstruccionTeor.tex:5`), "indentificación" (`3_Objetivos.tex:13`), "en la la mejora" (`3_Objetivos.tex:17`), "el Sistema Sistemas de soporte" (`2_Problema.tex:11`), "empresaial" (`0_Introduccion.tex:10`), "Sel-RAG" (`4_Justificacion+Alcance.tex:6`), "domínio" (`08_Capitulo02_ProyecMetodolo.tex:45`).
- **[m-02]** `0_Introduccion.tex:6`: oración subordinada sin oración principal ("En contextos industriales donde los datos operativos confidenciales […] no están disponibles públicamente."). Además, "son entrenados sobre entornos de la nube" es conceptualmente impreciso: los modelos se entrenan sobre corpus, y se sirven desde la nube.
- **[m-03]** `0_Introduccion.tex:8`: "mejor conocido en español como Generación Aumentada por Recuperación conocida" — duplicación.
- **[m-04]** `1_Antecedentes.tex:5`: el marco se nombra "Reflexión" (castellanizado) cuando su nombre propio es *Reflexion*; en el resto del documento aparece correctamente.
- **[m-05]** `3_Objetivos.tex:5`: las comillas de `''Critic-EmpRAG1.0''` abren con el carácter de cierre, de modo que el nombre aparece entre dos comillas de cierre.
- **[m-06]** `contenido/_images/img_smsProcess.tex` existe en el proyecto pero no se incluye en el documento; y `contenido/0_Abstract.tex` está comentado en el archivo principal. Conviene decidir si se incorporan o se retiran del proyecto.

---

## Hoja de ruta de correcciones

El orden importa: varias observaciones se resuelven con una misma acción y otras dependen de decisiones previas.

**Primera etapa — decidir qué se mide.** Resolver C-03 fijando una sola definición de cada variable; solo entonces reconstruir la Tabla 1 (C-02), porque la tabla depende de esa definición. Esta etapa desbloquea todo lo demás y es la que más trabajo conceptual exige.

**Segunda etapa — decidir cómo se demuestra.** Con la operacionalización cerrada, desdoblar la hipótesis (M-01) e incorporar los dos niveles de validación (C-01): el experimento ablativo para la afirmación científica y el preexperimento A₀→A₁ para la organizacional. De aquí se derivan, casi mecánicamente, M-02 (hipótesis de validación y fases), M-05 (pruebas estadísticas), M-06 (banco de evaluación como instrumento) y M-09 (alcance explicativo). Conviene tratarlas como un solo bloque de reescritura del Capítulo 2.

**Tercera etapa — cerrar los flancos del tribunal.** M-07 (amenazas a la validez), M-08 (transferibilidad), M-11 (modelo de amenazas de privacidad) y M-10 (protocolo Delphi). Son secciones nuevas o reformulaciones acotadas, independientes entre sí.

**Cuarta etapa — reestructurar antecedentes y añadir diagramas.** M-03 y M-04. Se dejan para el final porque son trabajo de redacción y representación que no depende de las decisiones anteriores, pero sí se beneficia de ellas: el diagrama de la propuesta será mejor una vez fijadas las variables.

**Transversal, ejecutable de inmediato.** C-04 (referencia inexistente), M-12 (citas manuales), M-13 (conector lógico) y las menores m-01 a m-06. Son correcciones puntuales que no dependen de nada y conviene aplicar cuanto antes, en particular C-04.

---

## Fortalezas

Cuatro elementos del perfil no deberían tocarse durante las correcciones.

1. **La cadena troncal superior es correcta y precisa.** El problema contiene explícitamente el objeto de estudio y el campo de acción; el objetivo general está construido con QUÉ (modelo crítico Critic-EmpRAG1.0), CÓMO (sobre arquitecturas de autorreflexión y RAG aplicadas a SLM), PARA QUÉ (mejora de la productividad y el acceso) y DÓNDE (Dualbiz SRL); y hay exactamente cuatro objetivos específicos en el orden exigido —teoría, diagnóstico, propuesta, validación—, cada uno con su verbo único y su alcance correspondiente. Es infrecuente encontrar este tramo tan bien resuelto.

2. **La novedad científica está formulada con precisión y es genuinamente defendible.** La distinción entre la competencia paramétrica para juzgar y el conocimiento no paramétrico sobre el cual se juzga, aplicada al componente crítico, es una extensión legítima y bien argumentada de la distinción que Lewis et al. (2020) formularon para el generador. El posicionamiento frente a Self-RAG y Self-BioRAG identifica con exactitud por qué ambas salidas resultan inaplicables al contexto estudiado. El aporte existe; el problema de este perfil es que el diseño no lo demuestra, no que el aporte sea débil.

3. **La justificación cubre los cinco criterios de la pauta** —conveniencia, relevancia social, implicaciones prácticas, valor teórico y utilidad metodológica— distribuidos en sus cuatro subsecciones, y responde tanto al porqué como al para qué.

4. **La fundamentación del vacío de conocimiento se apoya en un estudio de mapeo sistemático propio**, conducido sobre 40 estudios primarios entre 2020 y 2025 y ya publicado. Es una base considerablemente más sólida que la afirmación de novedad habitual en un perfil. Conviene, eso sí, actualizar la búsqueda antes de la defensa, dado que el campo se mueve rápido y el SMS cubre hasta 2025.
