# Escenarios sintéticos de evaluación

Estos escenarios son cronologías ficticias y minimalistas. No describen víctimas reales, no contienen datos personales y no deben leerse como una guía de ataque.

## Contrato de evaluación

Cada escenario separa:

- **Eventos observables:** los únicos datos que una regla puede usar.
- **Ground truth de laboratorio:** etiqueta retenida para evaluar; no está disponible para la regla.
- **Resultado esperado:** afirmaciones que la propuesta puede o no puede sostener.

Una propuesta no puede usar el ground truth para decidir. Si dos escenarios tienen las mismas observaciones y desenlaces distintos, el resultado correcto puede ser declarar que **no son distinguibles con esas señales**.

## S-01 — Secuencia con escalada financiera simulada

### Eventos observables

| Tiempo | Evento |
| ---: | --- |
| 00:00 | Una aplicación de mensajería pasa a primer plano. |
| 00:06 | Se instala una herramienta de asistencia remota conocida. |
| 00:08 | La herramienta de asistencia remota pasa a primer plano. |
| 00:12 | Una aplicación financiera pasa a primer plano. |

**Ground truth de laboratorio:** secuencia de riesgo simulada.

**Resultado esperado:** una propuesta puede elevar riesgo por la combinación observada. No puede afirmar que existe una sesión remota real ni que hubo una operación financiera.

## S-02 — Secuencia con escalada de identidad simulada

### Eventos observables

| Tiempo | Evento |
| ---: | --- |
| 00:00 | Una aplicación de mensajería pasa a primer plano. |
| 00:05 | Se instala una herramienta de asistencia remota conocida. |
| 00:07 | La herramienta de asistencia remota pasa a primer plano. |
| 00:11 | Una aplicación de correo o autenticación pasa a primer plano. |
| 00:14 | La aplicación de mensajería vuelve a primer plano. |

**Ground truth de laboratorio:** secuencia de riesgo simulada.

**Resultado esperado:** puede generarse una alerta de secuencia de riesgo; no una afirmación de toma de cuenta o de exposición de códigos.

## S-03 — Par benigno indistinguible de S-01

### Eventos observables

| Tiempo | Evento |
| ---: | --- |
| 00:00 | Una aplicación de mensajería pasa a primer plano. |
| 00:06 | Se instala una herramienta de asistencia remota conocida. |
| 00:08 | La herramienta de asistencia remota pasa a primer plano. |
| 00:12 | Una aplicación financiera pasa a primer plano. |

**Ground truth de laboratorio:** soporte legítimo simulado.

**Resultado esperado:** S-01 y S-03 no pueden distinguirse sólo con estos eventos. Una propuesta correcta debe reconocer el límite, solicitar verificación independiente o abstenerse de afirmar certeza.

## S-04 — Uso cotidiano sin señal de asistencia remota

### Eventos observables

| Tiempo | Evento |
| ---: | --- |
| 00:00 | Una aplicación de mensajería pasa a primer plano. |
| 00:04 | Se abre una aplicación de correo. |
| 00:10 | Se abre una aplicación financiera. |

**Ground truth de laboratorio:** uso cotidiano simulado.

**Resultado esperado:** no hay evidencia de esta modalidad de acceso remoto. El resultado no debe presentarse como “teléfono seguro” ni como ausencia de cualquier fraude.

## S-05 — Escalada con herramienta ya instalada

### Eventos observables

| Tiempo | Evento |
| ---: | --- |
| -72 h | Se instaló una herramienta de asistencia remota conocida. |
| 00:00 | La herramienta de asistencia remota pasa a primer plano. |
| 00:05 | Una aplicación financiera pasa a primer plano. |

**Ground truth de laboratorio:** secuencia de riesgo simulada.

**Resultado esperado:** la ausencia de instalación reciente no puede equivaler a bajo riesgo. Las propuestas deben declarar si cubren o no esta variante.

## S-06 — Respuesta bajo manipulación

### Eventos observables

Usá los eventos de S-01 hasta 00:08. Luego la persona descarta una advertencia local o intenta desactivar el mecanismo.

**Ground truth de laboratorio:** la decisión de la persona fue influida durante la simulación.

**Resultado esperado:** una propuesta de Deployment debe indicar qué protección, registro o canal independiente conserva utilidad. No se premia asumir que la persona obedecerá la alerta.

## Fuera de cobertura explícita

Una secuencia puede implicar riesgo sin incluir una herramienta remota del catálogo. Esos casos son válidos para demostrar límites de cobertura, pero no deben etiquetarse como seguros ni exigirse a una regla cuyo alcance declarado es acceso remoto conocido.

## Cómo extender el corpus

Las contribuciones pueden agregar escenarios si incluyen:

- evidencia o justificación clara;
- eventos observables separados del ground truth;
- al menos un comparador benigno cercano o una explicación de por qué no existe;
- resultado esperado verificable;
- información sintética, anonimizada y no operativa.