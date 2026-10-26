# Hoja de ruta de correcciones (tercera ronda) — Perfil doctoral Critic-EmpRAG1.0

**Fecha:** 20 de octubre de 2026 · **Versión base:** `PerfilLatexDocument/` (estado de trabajo al 20/10/2026)

**Fuentes consolidadas:**

| Sigla | Fuente | Archivo |
|---|---|---|
| **COM** | Evaluación del Comité Académico Doctoral (64.9/100, reformulación parcial) | `Evaluación Perfil - Leaños Rodriguez - 20261019.docx` |
| **GPT** | Matriz de perfeccionamiento elaborada con ChatGPT | `Matriz_Cuatro_Columnas_Perfil_DoctoralREVISION CHATGPT.pdf` |
| **V2** | Observaciones aún abiertas del informe de la segunda ronda | `informe-revision-leanos-perfil-doctoral-v2.md` |
| **REV** | Hallazgos de la revisión cruzada del `.tex` frente a COM y GPT | este documento |

> **Numeración.** Las observaciones abiertas de la v2 conservan su código (N-03, M-01…). Las nuevas de esta ronda llevan el prefijo **R**. Se mantiene la convención de un commit por observación.

---

## Etapa 0 — Agenda para la reunión con el Comité

Antes de tocar el alcance, conviene confirmar con el Comité los puntos que cambian la extensión del trabajo. Las etapas 1 a 4 no dependen de estas respuestas y pueden avanzar en paralelo; la etapa 5 sí.

1. **Segundo contexto de validación (R-20).** El Comité lo califica de "imprescindible", pero también admite "una combinación de caso y experimento controlado". Preguntar si es aceptable que el experimento controlado sea la réplica del segundo nivel (C1–C4b) sobre un *benchmark* público de soporte técnico (p. ej. TechQA), o si exige una segunda organización.
2. **Profundidad del cuerpo teórico (R-09).** Confirmar si basta, en el perfil, con enunciar proposiciones refutables con sus condiciones de aplicabilidad, ligadas a los contrastes C2→C3→C4 y a la ablación C4b, dejando su demostración a la tesis.
3. **Campo de acción (R-05).** Consultar si el Comité comparte que el campo debe ser una parte del objeto (mecanismos de juicio y refinamiento basados en evidencia recuperada) y no un resultado organizacional. Le asignó 0.8/2.
4. **Instrumentos estandarizados (R-16).** Confirmar si SUS y TAM son lo que espera o si acepta NASA-TLX para el esfuerzo percibido.

---

## Etapa 1 — Contradicciones, forma y división de la variable dependiente — **cerrada el 20/10/2026** (commits 2a13879, 1b51383, b2cbc50, 4a7458d)

La división de la VD (R-07) se adelanta a esta etapa por decisión del autor: al fijar primero las variables, la hipótesis (M-01 + R-08), la Tabla 1 y el análisis de los datos se redactan después sobre una base estable.

| Código | Fuente | Ubicación | Corrección |
|---|---|---|---|
| **R-01** | REV | `08_Capitulo02_ProyecMetodolo.tex:25`, Delimitación temática | Suprimir "utilizando un modelo propietario para extrapolar a un modelo de dominio específico". Contradice la novedad, que consiste precisamente en no depender de anotaciones de un modelo propietario. |
| **R-02** | GPT, REV | Nota de la Tabla 3 (`Cuadro3_ConfiguracionesValidacion.tex`) y `08_…:98` | Afirman que *todas* las configuraciones comparten el mecanismo de recuperación, pero C1 es "SLM sin recuperación". Reformular: comparten modelo base y corpus; C2 a C4b comparten además el recuperador y los parámetros de segmentación. |
| **R-03** | COM (redacción 1.2/3) | Varias | Errores puntuales: "domínio" (`08_…:47`), "computo" → "cómputo" (`3_Objetivos.tex:17`, `4_…:24`), "Dualbiz SRL. con restricciones" (`3_Objetivos.tex:17`), "tambien" (`4_…:24`), "se procesa" → "se procesan" (`08_…:126`). Restos de las menores de la v2: "especifico" (`6_…:5`, m-01) y "son entrenados sobre entornos de la nube" (`0_Introduccion.tex:6`, m-02). Pasada completa de redacción al cerrar la ronda. |
| **R-07** | COM (0/3), GPT | `6_…:7`, `08_…:43-58`, Tabla 1, `08_…:90-96` | Dividir la VD en dos variables: **VD₁ Productividad** del proceso de consulta (dimensión actual 2.2) y **VD₂ Acceso al conocimiento** (dimensiones actuales 2.1 Fundamentación y confiabilidad y 2.3 Viabilidad bajo restricciones), declarando cuáles son resultados primarios y cuáles condiciones de viabilidad. Redactar la definición conceptual de cada variable con fundamento en autores; hoy la VD es una definición propia y la VI se apoya en Shinn para un modelo que es del investigador. Propagar a la identificación de variables, a la Tabla 1 (renumerando dimensiones e indicadores) y a §Niveles de la validación empírica, donde VD₁ corresponde al primer nivel y VD₂ al segundo. La hipótesis se ajusta en la etapa 2. |

---

## Etapa 2 — Cadena troncal: problema, objetivos, hipótesis y variables — **hecha salvo R-05** (commits 0c45f16, 3d78f5a, 2a98531, 5296d6b)

Se redacta en este orden porque cada eslabón depende del anterior.

| Código | Fuente | Ubicación | Corrección |
|---|---|---|---|
| **R-04** | GPT | `2_Problema.tex` | Hacer explícito el vacío científico dentro de la formulación: la insuficiencia del juicio crítico en dominio específico bajo restricciones de privacidad y cómputo, y no solo la necesidad empresarial. |
| **R-05** | GPT, COM (0.8/2) | `2_Problema.tex:9` | *(Sujeto a la reunión, punto 4.)* Reformular el campo de acción como parte del objeto: mecanismos de juicio y refinamiento basados en evidencia recuperada, con Dualbiz SRL como contexto. Verificar que el nivel organizacional (A₀/A₁) conserve su anclaje en el objetivo y la hipótesis. Revisar a la vez el objeto (1.5/2), que GPT considera amplio. |
| **R-06** | COM, GPT | `3_Objetivos.tex:5` y `:15` | Objetivo general con verbo de nivel doctoral: **hecho el 20/10/2026** ("Diseñar" → "Implementar", por decisión del autor). Pendiente: OE3: "Diseñar e implementar…", haciendo explícito el prototipo. OE4: explicitar la evaluación por niveles. Propagar a la delimitación temporal (`08_…:35`). |
| **M-01** + **R-08** | V2, GPT, COM (3/4) | `6_FormulacionConstruccionTeor.tex:3` | Hipótesis con Hi/Ho/Ha que nombre el mecanismo explicativo: el anclaje del juicio del crítico en la evidencia recuperada → corrección → confiabilidad y productividad medibles. Debe quedar alineada con los dos niveles de validación y con las dos variables dependientes fijadas en R-07. |

---

## Etapa 3 — Contribución teórica y novedad

| Código | Fuente | Ubicación | Corrección |
|---|---|---|---|
| **R-09** | COM | `6_…:16`, Aporte teórico | **Hecho el 20/10/2026 (P1–P3 contrastables; P4 como línea de exploración).** Formular un cuerpo teórico verificable: principios, relaciones causales y condiciones de aplicabilidad que expliquen por qué y cuándo separar la competencia paramétrica del conocimiento no paramétrico mejora el juicio. Enunciarlos como proposiciones refutables ligadas a los contrastes, p. ej. *P1: el juicio del crítico sobre el dominio mejora cuando se ancla en evidencia recuperada; se refuta si C4b ≈ C4*. Condiciones candidatas: cobertura del recuperador, tamaño del modelo, vigencia del corpus. |
| **R-10** | COM, GPT | `6_…:35`, Novedad científica | Documentar la novedad con evidencia independiente del SMS propio: búsqueda complementaria 2025–2026 con protocolo explícito (bases, cadenas, criterios) y tabla comparativa frente a Self-RAG, Self-BioRAG, CRAG y trabajos recientes sobre críticos adaptativos. Profundizar el contraste con Self-BioRAG para descartar solapamientos. |
| **R-11** | GPT | `6_…:35` y Capítulo 1 | Especificar formalmente el crítico híbrido: algoritmo o flujo de decisión, señales que emite, umbrales y condición de activación del ciclo correctivo. Se resuelve junto con M-04 (diagramas). |
| **R-12** | COM (0.5/2) | `4_Justificacion+Alcance.tex:24` | **Hecho el 20/10/2026.** Reescribir la justificación metodológica sobre lo que el Comité valoró: diseño en dos niveles, ablaciones, amenazas a la validez declaradas y procedimiento replicable. Retirar la afirmación vaga de que los SLM "puedan ser más eficientes que los modelos generalizados". |

---

## Etapa 4 — Bloque de la validación

| Código | Fuente | Ubicación | Corrección |
|---|---|---|---|
| **N-03** + **M-06** | V2, COM | §Instrumentos (`08_…:111`), §Población y muestra (`08_…:121`) | Especificar el banco de evaluación: número de consultas, criterios de estratificación, proporción de consultas sin respaldo en el corpus, proceso de construcción a partir de tickets reales y quién establece la verdad de referencia. |
| **R-13** | GPT, COM (1.2/3) | §Población y muestra | Distinguir las unidades de análisis (persona, consulta, sesión, ejecución) y su cantidad. Declarar las repeticiones por la estocasticidad del modelo (semillas, temperatura) y cómo se agregan las consultas de una misma persona en el primer nivel. |
| **M-14** + **R-14** | V2, GPT | §Técnicas (`08_…:104`), Tabla 1 (3.1.2, 3.1.4) | Protocolo de anotación de los indicadores de alucinación y fidelidad, con **evaluación humana ciega** sobre una submuestra. Incorporar que la fidelidad a la fuente no implica verdad factual: vigencia documental y tratamiento de evidencia contradictoria. |
| **R-15** | GPT | §Métodos del nivel empírico (`08_…:78`) | Estandarizar el preexperimento: tareas equivalentes en A₀ y A₁, periodos de medición, entrenamiento previo en el uso del prototipo, registro y límites de la inferencia causal. |
| **M-02** | V2 | §Métodos del nivel empírico | Hipótesis de validación y fases del proceso experimental. |
| **R-16** | COM (1.2/3), GPT | §Instrumentos (`08_…:111`) | Añadir instrumentos estandarizados: SUS (usabilidad), TAM (aceptación) y NASA-TLX para el esfuerzo percibido (indicador 2.3.1). Añadir los instrumentos computacionales: banco de evaluación, protocolo de anotación y registro automático de latencia y consumo de cómputo. Revisar las técnicas (1.2/3) en consecuencia. |
| **R-17** | GPT, COM (1.2/3) | §Análisis de los datos (`08_…:125`) | Ya cubre tamaños de efecto, IC y comparaciones múltiples. Falta tratar la dependencia entre observaciones (varias consultas por persona, varias ejecuciones por consulta) y la integración entre los hallazgos cualitativos y la interpretación cuantitativa del enfoque mixto. |
| **R-18** | GPT | Delimitación temática (`08_…:27`), indicador 3.2.4 | Añadir pruebas explícitas de amenazas propias de RAG: fuga entre roles, *prompt injection* y trazabilidad. Una línea en el inventario de superficies y su reflejo en el indicador, sin ampliar el alcance. |
| **M-10** | V2, GPT | §Consulta a expertos (`08_…:75`) | Completar el protocolo Delphi: número de rondas, criterio de consenso (p. ej. W de Kendall), instrumento. Nombrarlo **valoración teórica**, ya que el juicio experto no prueba la efectividad del prototipo. |
| **R-19** | GPT | §Perspectiva epistemológica (`08_…:3`), §Enfoque (`08_…:13`) | Separar la postura epistemológica de la lógica de diseño y de los criterios de evidencia. Precisar el diseño (1.2/3). Prioridad baja. |

---

## Etapa 5 — Alcance de la validación *(depende de la reunión con el Comité)*

| Código | Fuente | Ubicación | Corrección |
|---|---|---|---|
| **R-20** | COM ("imprescindible") | Delimitación espacial (`08_…:29`), Validez externa (`08_…:142`), Población y muestra, Justificación práctica | Incorporar el segundo contexto que acuerde el Comité: una segunda organización, o la réplica del segundo nivel sobre un *benchmark* público. Si el Comité no lo exige, argumentar con fuerza por qué las ablaciones C1–C4b bastan para el nivel doctoral. En ambos casos, reformular la delimitación espacial (0.8/2) y la validez externa. |
| **R-21** | COM (0.8/2) | `Cuadro2_CronogramaInvestigacion.tex` | Rehacer el cronograma con las actividades que añaden R-10, R-16 y R-20. Hacerlo al final, cuando el alcance esté cerrado. |

---

## Etapa 6 — Secciones faltantes y bibliografía

| Código | Fuente | Ubicación | Corrección |
|---|---|---|---|
| **M-03** | V2 | `1_Antecedentes.tex` | Reestructurar los antecedentes e incorporar el árbol de problemas. |
| **M-04** | V2, GPT | Varias | Diagramas: arquitectura del modelo crítico, flujo de decisión del crítico híbrido (R-11) y diseño de validación en dos niveles. |
| **R-22** | COM (0.8/3) | Capítulo 1 (`7_Capitulo01…:47`) | Componentes y elementos tecnológicos: pasar de familias genéricas a componentes concretos (recuperador, modelo de *embeddings*, índice vectorial, *framework* de orquestación). Los SLM quedan en la etapa 7. |
| **R-23** | COM (0.8/2) | `InductiveLearning-PHD-perfil2.tex:97` | El documento no tiene **bibliografía complementaria**: solo imprime las obras citadas. Añadir una sección con `\nocite` o una segunda lista filtrada. |
| **R-24** | COM (2.25/3), GPT | `_bibliografia.bib` | Verificar identificadores, URL, año, venue y alcance de cada referencia, e incorporar la literatura 2025–2026 que surja de R-10. |

---

## Etapa 7 — Para revisión al final

Estos puntos requieren decisiones técnicas que se toman después de la reunión con el Comité y con el inventario de *hardware* disponible.

| Código | Fuente | Decisión pendiente |
|---|---|---|
| **R-25** | REV | **Hardware disponible.** GPU, memoria y servidor *on-premise* de Dualbiz SRL. Condiciona R-26 y R-27, y alimenta el indicador 3.2.2. |
| **R-26** | COM | **Elección y justificación de los SLM concretos** (hoy "p. ej. LLaMA, Mistral, Phi, Gemma", `7_Capitulo01…:47`). Criterios: tamaño compatible con el *hardware*, licencia, desempeño en español y disponibilidad de versiones *instruct*. |
| **R-27** | GPT, REV | **Comparabilidad de C3 (Self-RAG).** Sus pesos publicados son Llama-2 7B y 13B con el crítico ya entrenado. Para que C3 y C4 compartan el modelo base hay dos opciones: (a) usar Llama-2-7B como base común de todas las configuraciones, o (b) reentrenar Self-RAG sobre el SLM elegido con su *dataset* público. La opción (b) choca con la delimitación temática, que excluye el ajuste fino, y debería declararse como excepción acotada a la línea base. Se decide junto con R-26. |

---

## Resumen

| Etapa | Contenido | Depende de |
|---|---|---|
| 0 | Reunión con el Comité | — |
| 1 | R-01, R-02, R-03, R-07 | — |
| 2 | R-04, R-05, R-06, M-01 + R-08 | R-07; reunión (R-05) |
| 3 | R-09, R-10, R-11, R-12 | Etapa 2 |
| 4 | N-03 + M-06, R-13, M-14 + R-14, R-15, M-02, R-16, R-17, R-18, M-10, R-19 | Etapa 2 |
| 5 | R-20, R-21 | Reunión |
| 6 | M-03, M-04, R-22, R-23, R-24 | R-11, R-10 |
| 7 | R-25, R-26, R-27 | Reunión y *hardware* |

Quedan cerradas de la v2: N-01, N-02, N-04, M-05 (vía N-01), M-11, m-03 y m-04. Lo que resta de m-01 y m-02 se absorbe en R-03.
