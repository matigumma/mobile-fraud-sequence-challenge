# Rúbrica de evaluación

La evaluación tiene dos etapas: primero gates de seguridad y método; después una puntuación de 0 a 20. Un promedio alto no compensa una falla fundamental.

## Gates obligatorios

| Gate | Requisito |
| --- | --- |
| Separación de capas | La propuesta distingue eventos observables, inferencias y ground truth. |
| Datos y seguridad | No usa contenido sensible, datos reales de víctimas ni material que incremente capacidad ofensiva. |
| Comparación honesta | Se evalúa contra un par benigno cercano o reconoce que los casos son indistinguibles. |
| Manipulación | Declara qué decisiones del usuario puede inducir o neutralizar un atacante. |
| Límite de cobertura | No presenta ausencia de señal como ausencia de fraude. |
| Ancla independiente | Sólo para Deployment: explica qué canal, persona o institución permanece fuera del control de la misma sesión y su modo de falla. |

Una propuesta que no supera un gate no puede ser Candidate, aunque su puntuación sea alta.

## Puntuación

| Criterio | Pregunta | 0 puntos | 3 puntos | 5 puntos |
| --- | --- | --- | --- | --- |
| Detectabilidad | ¿La propuesta usa señales realmente observables bajo la pista declarada? | Depende de un dato inaccesible o trata una inferencia como observación. | Usa una señal permitida con límites relevantes. | Declara señales mínimas, cobertura y límites con precisión. |
| Anticipación | ¿Cuánto antes de una acción de alto impacto entrega información útil? | Sólo concluye después del daño o de una etiqueta de laboratorio. | Aporta información durante la secuencia, con poco margen. | Aporta información antes de una acción sensible o demuestra honestamente que no hay anticipación posible. |
| Discriminación | ¿Cómo se comporta frente al uso legítimo más parecido? | No evalúa pares benignos ni falsos positivos. | Reconoce algunos comparadores y límites. | Explica resultados ante pares cercanos e identifica cuándo los eventos no bastan para distinguir. |
| Resiliencia frente a manipulación | ¿Sigue siendo honesta y útil si el atacante induce permisos, excepciones o descartes? | Depende de que la persona no sea manipulada. | Reconoce algunos bypasses, sin respuesta clara. | Explicita las decisiones manipulables, el modo de falla y una respuesta independiente o el límite inevitable. |

## Estados

| Total y gates | Estado | Significado |
| --- | --- | --- |
| 0–8 | Hypothesis | Idea inicial; falta evidencia, observabilidad o evaluación. |
| 9–13 con gates aplicables | Test-ready | Puede probarse con escenarios sintéticos. |
| 14–20, pista Research y gates aplicables | Research result | Conclusión reproducible sobre valor, límite o imposibilidad de una señal. No implica despliegue. |
| 14–20, pista Deployment y todos los gates | Deployment candidate | Merece un prototipo limitado o validación adicional; no es una garantía de protección. |

## Condiciones eliminatorias

Una propuesta queda rechazada si:

- requiere leer o almacenar chats, llamadas, correos, contraseñas, códigos de verificación o capturas de pantalla;
- usa datos de víctimas, cuentas reales, teléfonos de terceros o pruebas sin consentimiento válido y contexto de laboratorio;
- presenta una excepción voluntaria como control de seguridad suficiente;
- afirma una toma de control, sesión remota o daño financiero sin evidencia observable para esa afirmación;
- no evalúa al menos un escenario de riesgo y un par benigno cercano;
- publica información personal, activos de fraude o detalles que faciliten abuso.

## Registro de resultados

Toda evaluación debe indicar:

- versión de la propuesta y pista elegida;
- escenarios usados y observaciones disponibles;
- gates aprobados, rechazados o no aplicables;
- puntaje por criterio y justificación;
- incertidumbres, falsos positivos, falsos negativos y cobertura;
- decisión: mantener como hipótesis, preparar prueba, registrar resultado de Research, promover a Deployment candidate, archivar o rechazar.