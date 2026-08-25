# Escenarios sintéticos de evaluación

Estos escenarios son cronologías ficticias y minimalistas. No describen víctimas reales, no contienen datos personales y no deben leerse como una guía de ataque.

Una propuesta debe indicar el nivel de riesgo y el momento en que alertaría para **cada** escenario.

## S-01 — Escalada financiera

| Tiempo | Evento |
| ---: | --- |
| 00:00 | Una aplicación de mensajería pasa a primer plano. |
| 00:06 | Se instala una herramienta de asistencia remota. |
| 00:08 | La herramienta de asistencia remota pasa a primer plano. |
| 00:12 | Una aplicación financiera pasa a primer plano. |

**Resultado de referencia:** riesgo alto al activar la herramienta remota; alerta crítica, como máximo, antes del evento financiero.

## S-02 — Escalada de identidad y mensajería

| Tiempo | Evento |
| ---: | --- |
| 00:00 | Una aplicación de mensajería pasa a primer plano. |
| 00:05 | Se instala una herramienta de asistencia remota. |
| 00:07 | La herramienta de asistencia remota pasa a primer plano. |
| 00:11 | Una aplicación de correo o autenticación pasa a primer plano. |
| 00:14 | La aplicación de mensajería vuelve a primer plano. |

**Resultado de referencia:** no afirmar toma de cuenta; clasificar como secuencia de alto riesgo y pedir intervención humana antes de que el acceso remoto deje de ser reversible.

## S-03 — Soporte remoto legítimo

| Tiempo | Evento |
| ---: | --- |
| 00:00 | La persona inicia una sesión de asistencia remota previamente acordada. |
| 00:03 | La herramienta de asistencia remota pasa a primer plano. |
| 00:12 | Se abre la aplicación de configuración del dispositivo. |
| 00:20 | La herramienta de asistencia remota se cierra. |

**Resultado de referencia:** no enviar una alerta externa urgente. Una advertencia local o confirmación de contexto puede ser admisible si está diseñada para no alarmar.

## S-04 — Uso cotidiano sin acceso remoto

| Tiempo | Evento |
| ---: | --- |
| 00:00 | Una aplicación de mensajería pasa a primer plano. |
| 00:04 | Se abre una aplicación de correo. |
| 00:10 | Se abre una aplicación financiera. |

**Resultado de referencia:** sin alerta de toma de control remoto.

## Cómo extender el corpus

Las contribuciones pueden agregar escenarios si incluyen:

- una fuente o justificación clara;
- al menos un caso benigno comparable;
- eventos que una aplicación Android común podría distinguir de forma razonable;
- un resultado esperado verificable;
- información anonimizada y no operativa.