# Plantilla de propuesta

Copiá esta plantilla en un issue o pull request. Las secciones marcadas como obligatorias deben estar completas para que la propuesta pueda evaluarse.

## Título

`PSR-XXXX — nombre breve de la secuencia o regla`

## Resumen — obligatorio

Explicá en dos o tres frases qué secuencia intentás identificar y qué alerta o intervención proponés.

## Cadena de riesgo — obligatorio

Describí los eventos en orden temporal, a nivel defensivo y sin instrucciones operativas de fraude.

## Evidencia — obligatorio

- Fuentes oficiales:
- Prensa o investigación especializada:
- Reportes comunitarios o casos anonimizados:
- Qué parte de la hipótesis está confirmada y cuál sigue siendo inferencia:

## Señales técnicamente observables — obligatorio

| Señal | Cómo se observaría | Permiso o limitación | Fuerza de la señal |
| --- | --- | --- | --- |
| | | | |

## Señales no observables o excluidas — obligatorio

Indicá explícitamente qué no podés, no debés o no necesitás conocer: contenido de llamadas, chats, códigos, credenciales, acciones dentro de una cuenta u otros datos sensibles.

## Regla propuesta — obligatorio

Definí la lógica, el orden de las señales, las ventanas de tiempo y el nivel de riesgo. Puede ser pseudocódigo, una tabla o una explicación precisa.

## Resultado esperado contra escenarios — obligatorio

| Escenario | Riesgo esperado | Momento máximo de alerta | Justificación |
| --- | --- | --- | --- |
| | | | |

## Falsos positivos previsibles — obligatorio

- Caso benigno que podría activar la regla:
- Impacto para la persona:
- Cómo se reduce la confusión sin invadir privacidad:

## Acción de protección — obligatorio

¿Qué debería hacer la persona, un contacto de confianza o una institución cuando se active la alerta? La acción debe ser concreta y no requerir que el teléfono comprometible siga siendo confiable.

## Privacidad y datos mínimos — obligatorio

- Datos observados:
- Datos que no se recolectan:
- Retención propuesta:
- Riesgo de abuso y mitigación:

## Autoevaluación

| Criterio | Puntaje de 0 a 5 | Explicación breve |
| --- | ---: | --- |
| Detectabilidad | | |
| Anticipación | | |
| Falsos positivos | | |
| Acción útil | | |
| **Total** | **/20** | |