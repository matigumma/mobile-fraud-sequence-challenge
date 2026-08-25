# Challenge 001 — Resiliencia ante secuencias de toma de control remoto

## Objetivo

Estudiar reglas, señales o mecanismos de alerta que ayuden a reconocer una secuencia compatible con toma de control remoto **sin confundir correlación con certeza** y sin depender de que la persona pueda resistir una instrucción engañosa.

## Pregunta de trabajo

> Bajo el supuesto de que un atacante puede inducir a la persona a instalar apps, otorgar permisos, declarar una sesión como legítima, ignorar alertas y cambiar preferencias desde el dispositivo, ¿qué señales o anclas independientes permiten una intervención útil?

## Modelo de partida

La investigación parte de campañas de ingeniería social en las que una persona puede instalar una herramienta legítima de asistencia remota y luego abrir una aplicación financiera, de identidad o de mensajería. Eso no permite afirmar que cada secuencia equivalente sea fraudulenta.

La distinción entre estos tres niveles es obligatoria:

| Nivel | Ejemplo | Tratamiento correcto |
| --- | --- | --- |
| **Observación** | Una app conocida se instala o pasa a primer plano. | Puede alimentar una regla, si está técnicamente disponible. |
| **Inferencia** | Podría existir una sesión de asistencia remota. | Debe presentarse como hipótesis, no como hecho. |
| **Daño / ground truth** | Hubo una toma de cuenta o una operación financiera simulada. | Sólo se usa para evaluar un escenario de laboratorio. |

## Pistas de contribución

### Research

Responde: **¿una señal o combinación mejora la capacidad de distinguir, o demuestra que no puede distinguirse?**

- Usa solamente cronologías sintéticas, dispositivos de prueba y cuentas ficticias.
- Puede estudiar una señal aunque todavía no sea apta para producto.
- Debe declarar por qué el resultado no constituye una promesa de despliegue.
- Puede concluir correctamente: “con estas observaciones no es identificable”.

### Deployment

Responde: **¿la idea debería transformarse en una función para personas reales?**

- Sólo puede usar señales mínimas, consentidas y compatibles con una aplicación Android convencional.
- Debe separar lo que es técnicamente posible de lo que sería aceptable, proporcional y compatible con plataforma.
- Debe indicar qué ocurre si el usuario es persuadido para descartar la alerta, retirar permisos o declarar una excepción.
- Debe definir una intervención y su modo de falla; no puede afirmar que una notificación en el mismo teléfono resuelve el riesgo.

## Límites comunes

- No usar datos de víctimas, cuentas, teléfonos, credenciales, códigos, mensajes, audio de llamadas ni capturas reales.
- No producir ni publicar instrucciones que habiliten, escalen o evadan fraude.
- No tratar una app, un permiso o una excepción voluntaria como evidencia suficiente de legitimidad.
- No afirmar control remoto activo, transferencia, toma de Google o toma de WhatsApp si sólo se observó una cronología de apps.
- No usar una contribución educativa como justificación para crear vigilancia sobre personas reales.

## Entregable

Cada propuesta debe incluir:

1. Pista elegida: Research o Deployment.
2. Cadena de riesgo, evidencia y nivel de confianza de cada afirmación.
3. Separación entre eventos observables, inferencias y ground truth de laboratorio.
4. Regla, mecanismo de evaluación o hipótesis de imposibilidad.
5. Resultado frente a todos los escenarios publicados y, especialmente, frente a sus pares cercanos.
6. Falsos positivos, falsos negativos y situaciones fuera de cobertura.
7. Prueba de resistencia a manipulación: qué decisiones puede inducir el atacante.
8. Para Deployment, una acción concreta, un ancla independiente y un modo de falla explícito.

Usá [proposal-template.md](proposal-template.md) y [scorecard.md](scorecard.md).

## Éxito medible

### Resultado de Research

Una propuesta es un resultado valioso si supera los gates de método, obtiene al menos 14/20 o demuestra de forma reproducible que dos desenlaces distintos son indistinguibles con las mismas observaciones disponibles.

### Candidate de Deployment

Una propuesta llega a Candidate sólo si:

- supera todos los gates aplicables;
- obtiene al menos 14/20;
- no exige contenido sensible ni capacidades incompatibles con su declaración de despliegue;
- no depende de que el usuario manipulado confirme, descarte o configure una excepción para mantenerse segura;
- explica qué persona, sistema o canal conserva independencia cuando el teléfono deja de ser confiable.

## Resultado esperado del primer ciclo

El proyecto puede producir una regla útil, un mejor escenario, una frontera técnica, una hipótesis descartada o evidencia de que sería necesaria otra autoridad —por ejemplo, un banco, una plataforma o un dispositivo administrado—. Todos son resultados válidos.