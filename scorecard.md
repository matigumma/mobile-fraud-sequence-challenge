# Rúbrica de evaluación

Cada propuesta recibe de 0 a 5 puntos en cuatro criterios. El total máximo es 20.

| Criterio | Pregunta | 0 puntos | 3 puntos | 5 puntos |
| --- | --- | --- | --- | --- |
| Detectabilidad | ¿Una aplicación Android convencional puede observar la señal? | Depende de contenido privado o una capacidad no disponible. | Usa una señal permitida pero con límites o permisos relevantes. | Usa señales claramente disponibles, consentidas y mínimas. |
| Anticipación | ¿Cuánto antes de un daño serio puede alertar? | Sólo detecta algo después de la acción irreversible. | Alerta durante la secuencia, pero con poco margen. | Alerta antes de abrir el activo sensible o de una acción de alto impacto. |
| Falsos positivos | ¿Cómo se comporta ante uso legítimo? | Se dispara con frecuencia o no analiza escenarios benignos. | Reconoce algunos casos benignos, con mitigación parcial. | Distingue bien los comparadores benignos y explica sus límites. |
| Acción útil | ¿La alerta permite una intervención real? | No existe una acción o sólo muestra un aviso genérico. | Propone una acción posible pero dependiente del teléfono comprometible. | Activa una acción clara, o una alerta fuera del dispositivo, que alguien puede ejecutar. |

## Umbrales

| Total | Estado | Significado |
| ---: | --- | --- |
| 0–8 | Hypothesis | Idea inicial; falta evidencia, observabilidad o evaluación. |
| 9–13 | Test-ready | Puede probarse, pero aún no justifica promoción. |
| 14–20 | Candidate | Merece comparación, prototipo limitado o validación adicional. |

## Condiciones eliminatorias

Una propuesta queda descartada, sin importar su puntaje, si:

- requiere leer o almacenar chats, llamadas, correos, contraseñas, códigos de verificación o capturas de pantalla;
- depende de permisos, administración del dispositivo o capacidades que no correspondan a una aplicación Android convencional sin explicitarlo;
- no presenta al menos un escenario de riesgo y dos comparadores benignos;
- no explica qué acción concreta sigue a la alerta;
- publica información personal de víctimas o detalles que faciliten un fraude.

## Registro de resultados

Toda evaluación debe indicar:

- versión de la propuesta;
- escenarios usados;
- puntaje por criterio y justificación;
- discrepancias entre revisores;
- decisión: mantener como hipótesis, preparar prueba, promover a candidata, archivar o rechazar.