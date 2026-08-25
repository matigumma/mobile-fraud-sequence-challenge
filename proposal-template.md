# Plantilla de propuesta

Copiá esta plantilla en un issue o pull request. Las secciones obligatorias deben estar completas para que una propuesta pueda evaluarse.

## Título

`PSR-XXXX — nombre breve de la hipótesis, regla o límite`

## Pista — obligatorio

- [ ] Research
- [ ] Deployment

Explicá por qué corresponde a esa pista y qué afirmación **no** hace tu propuesta.

## Resumen — obligatorio

Explicá qué intentás medir, distinguir, limitar o intervenir. No afirmes certeza de fraude si sólo observás una secuencia.

## Cadena de riesgo y evidencia — obligatorio

- Fuentes oficiales:
- Prensa o investigación especializada:
- Reportes comunitarios o casos anonimizados:
- Qué está confirmado:
- Qué sigue siendo inferencia:
- Nivel de confianza:

## Separación de capas — obligatorio

| Capa | Señal, hipótesis o resultado | Cómo se obtiene | Puede usarla la regla |
| --- | --- | --- | --- |
| Evento observable | | | Sí / No |
| Inferencia | | | No como hecho |
| Ground truth de laboratorio | | | No |
| Daño real que no puede observarse | | | No |

## Regla, experimento o hipótesis de imposibilidad — obligatorio

Definí la lógica, ventanas temporales y nivel de riesgo. Una propuesta de Research puede demostrar que una señal no alcanza; una de Deployment debe declarar sus límites de cobertura.

## Resultado contra escenarios — obligatorio

| Escenario | Salida de la propuesta | Afirmación permitida | Límite o incertidumbre |
| --- | --- | --- | --- |
| S-01 | | | |
| S-02 | | | |
| S-03 | | | |
| S-04 | | | |
| S-05 | | | |
| S-06 | | | |

## Prueba de resistencia a manipulación — obligatorio

- ¿Qué permisos, excepciones, avisos o preferencias podría inducir el atacante?
- ¿Qué parte de la propuesta seguiría funcionando si la persona confirma o descarta algo bajo presión?
- ¿Qué parte puede neutralizarse?
- ¿Cuál es el modo de falla seguro y cómo se comunica?

## Falsos positivos, falsos negativos y cobertura — obligatorio

- Par benigno más parecido:
- Falso positivo previsto:
- Falso negativo previsto:
- Modalidades explícitamente fuera de cobertura:

## Acción de protección — obligatorio sólo para Deployment

- Acción para la persona:
- Acción para una institución o canal externo:
- Ancla independiente del teléfono:
- Cómo se establece, cambia y revoca:
- Qué ocurre si no responde o no es confiable:

## Privacidad, seguridad y datos mínimos — obligatorio

- Datos observados:
- Datos que no se recolectan:
- Datos sintéticos usados en Research, si aplica:
- Retención propuesta:
- Riesgo de abuso y mitigación:

## Autoevaluación

| Gate | Pasa / No pasa / No aplica | Justificación |
| --- | --- | --- |
| Separación observación–inferencia–ground truth | | |
| No usa contenido sensible ni datos reales | | |
| Prueba contra un par benigno cercano | | |
| Declara manipulación posible y modo de falla | | |
| Ancla independiente para Deployment | | |

| Criterio | Puntaje de 0 a 5 | Explicación breve |
| --- | ---: | --- |
| Detectabilidad | | |
| Anticipación | | |
| Discriminación | | |
| Resiliencia frente a manipulación | | |
| **Total** | **/20** | |