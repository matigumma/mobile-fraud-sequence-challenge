# Ejemplo de contribución — PSR-0001

## Pista

**Research**

Este ejemplo muestra cómo documentar una conclusión negativa útil. No propone una función de producto, no procesa datos reales y no afirma detectar fraude.

## Título

`PSR-0001 — La secuencia remota-financiera no es identificable sólo por cronología de apps`

## Resumen

S-01 y S-03 tienen exactamente los mismos eventos observables, pero distinto ground truth de laboratorio. Por lo tanto, una regla que sólo recibe esos eventos no puede clasificar uno como fraude y el otro como soporte legítimo con certeza.

La conclusión de esta propuesta no es “no hay riesgo”. Es: **la cronología por sí sola puede justificar una señal de ambigüedad o una verificación independiente, pero no una afirmación de fraude.**

## Cadena de riesgo y evidencia

- Fuentes oficiales: no aplica; este ejemplo evalúa la estructura metodológica del corpus sintético.
- Prensa o investigación especializada: no aplica.
- Reportes comunitarios o casos anonimizados: no aplica.
- Qué está confirmado: S-01 y S-03 comparten los mismos eventos observables declarados.
- Qué sigue siendo inferencia: la intención de quien brinda asistencia y la existencia de un riesgo real.
- Nivel de confianza: alto para la conclusión metodológica dentro de estos escenarios.

## Separación de capas

| Capa | Señal, hipótesis o resultado | Cómo se obtiene | Puede usarla la regla |
| --- | --- | --- | --- |
| Evento observable | Mensajería en primer plano; instalación y apertura de una herramienta remota conocida; aplicación financiera en primer plano. | Cronología sintética de S-01 y S-03. | Sí |
| Inferencia | “Hay una sesión remota activa” o “la persona está siendo engañada”. | Interpretación de la cronología. | No como hecho |
| Ground truth de laboratorio | S-01 representa riesgo simulado y S-03 soporte legítimo simulado. | Etiqueta retenida para evaluación. | No |
| Daño real que no puede observarse | Transferencia, exposición de credenciales o toma de cuenta. | No está presente en la cronología. | No |

## Regla, experimento o hipótesis de imposibilidad

### Experimento

1. Entregar a la regla sólo los eventos observables de S-01 y S-03.
2. Verificar que los vectores de entrada sean iguales.
3. Comparar cualquier salida determinista de la regla.

### Resultado

No existe una clasificación basada únicamente en esta cronología que pueda ser correcta para ambos ground truths. La salida permitida es una de estas:

- `secuencia ambigua de riesgo`;
- `requiere señal independiente`;
- `no identificable con las observaciones disponibles`.

Las salidas `fraude confirmado` y `sesión legítima confirmada` no están justificadas.

## Resultado contra escenarios

| Escenario | Salida de la propuesta | Afirmación permitida | Límite o incertidumbre |
| --- | --- | --- | --- |
| S-01 | Secuencia ambigua de riesgo. | La combinación puede ameritar verificación independiente. | No prueba sesión remota ni daño. |
| S-02 | Fuera de la hipótesis específica. | Puede registrarse como otra secuencia de escalada a estudiar. | No permite inferir toma de identidad. |
| S-03 | Secuencia ambigua de riesgo. | Tiene la misma entrada observable que S-01. | No permite confirmar legitimidad. |
| S-04 | Sin evidencia de esta modalidad. | No se observan las señales del experimento. | No equivale a teléfono seguro. |
| S-05 | Cobertura parcial. | La instalación reciente no es una condición necesaria del riesgo. | Esta hipótesis no resuelve software ya instalado. |
| S-06 | No depende de una alerta aceptada. | El resultado Research sigue siendo válido aunque la persona descarte un aviso. | No define intervención de producto. |

## Prueba de resistencia a manipulación

- ¿Qué podría inducir el atacante? Que la persona declare la sesión como legítima, descarte una advertencia o cambie una preferencia.
- ¿Qué sigue funcionando? La conclusión metodológica: esa declaración no agrega una señal independiente que permita distinguir S-01 de S-03.
- ¿Qué puede neutralizarse? Cualquier alerta local basada sólo en la misma cronología y en decisiones tomadas desde el mismo teléfono.
- Modo de falla seguro: no convertir ambigüedad en una acusación ni en una promesa de protección.

## Falsos positivos, falsos negativos y cobertura

- Par benigno más parecido: S-03.
- Falso positivo previsto: tratar S-03 como fraude.
- Falso negativo previsto: tratar S-01 como soporte legítimo.
- Modalidades explícitamente fuera de cobertura: secuencias sin herramienta remota conocida, sesiones que no puedan observarse mediante el catálogo y cualquier resultado dentro de otra aplicación.

## Acción de protección

No aplica: ésta es una propuesta de Research. El resultado indica que cualquier futura propuesta de Deployment necesitaría una señal o ancla independiente para distinguir ambos casos.

## Privacidad, seguridad y datos mínimos

- Datos observados: únicamente eventos sintéticos declarados en S-01 y S-03.
- Datos que no se recolectan: comunicaciones, códigos, credenciales, capturas, datos de víctimas o cuentas reales.
- Datos sintéticos usados en Research: cronologías del repositorio.
- Retención propuesta: no aplica; no se genera telemetría.
- Riesgo de abuso y mitigación: el ejemplo describe un límite defensivo, no instrucciones para reproducir fraude.

## Autoevaluación

| Gate | Pasa / No pasa / No aplica | Justificación |
| --- | --- | --- |
| Separación observación–inferencia–ground truth | Pasa | Las etiquetas de S-01 y S-03 no se usan como entrada. |
| No usa contenido sensible ni datos reales | Pasa | Usa únicamente cronologías sintéticas. |
| Prueba contra un par benigno cercano | Pasa | S-03 comparte exactamente las observaciones de S-01. |
| Declara manipulación posible y modo de falla | Pasa | Las decisiones de la persona se consideran manipulables. |
| Ancla independiente para Deployment | No aplica | La propuesta no es de Deployment. |

| Criterio | Puntaje de 0 a 5 | Explicación breve |
| --- | ---: | --- |
| Detectabilidad | 5 | Usa sólo las observaciones entregadas por el escenario. |
| Anticipación | 4 | Identifica el límite antes de afirmar una acción de alto impacto. |
| Discriminación | 5 | Demuestra correctamente que los eventos disponibles no discriminan S-01 y S-03. |
| Resiliencia frente a manipulación | 5 | No confía en una excepción voluntaria como control de seguridad. |
| **Total** | **19/20** | **Research result; no implica candidato de Deployment.** |

## Conclusión

La cronología de aplicaciones puede ser una señal de contexto, pero no una prueba de fraude. Para convertir este hallazgo en una intervención de producto habría que aportar una señal independiente, un canal externo confiable o una integración que cambie realmente la información disponible.