# Mobile Fraud Sequence Challenge

Un desafío abierto, educativo y acotado para estudiar defensas tempranas frente a secuencias de toma de control de teléfonos móviles mediante ingeniería social.

> No buscamos prometer que una aplicación "detecta estafas". Buscamos establecer qué señales son observables, cuáles no permiten distinguir fraude de uso legítimo y qué intervención podría seguir siendo útil cuando el usuario está bajo manipulación.

## La pregunta central

**Bajo el supuesto de que un atacante puede inducir a una persona a instalar apps, otorgar permisos, ignorar avisos y cambiar preferencias desde el mismo teléfono, ¿qué señales o anclas de confianza independientes todavía permiten intervenir?**

El punto de partida son fraudes en los que una persona es inducida a instalar una herramienta legítima de asistencia remota y, luego, a abrir servicios financieros, correo, cuenta Google o WhatsApp.

## Principios del desafío

- El consentimiento no prueba legitimidad: en este modelo de amenaza puede ser inducido por el atacante.
- Un evento observable no prueba una intención ni un daño. La propuesta debe separar **observación**, **inferencia** y **ground truth de laboratorio**.
- Una señal aislada no prueba una estafa. Incluso una secuencia completa puede ser indistinguible de un uso legítimo.
- Los resultados de investigación y las funciones desplegables son cosas distintas.
- No se recopilan ni procesan mensajes, audio de llamadas, contraseñas, códigos de verificación, capturas de pantalla ni contenido de correo.
- Una respuesta de protección sólo es robusta si identifica qué componente sigue siendo confiable cuando el teléfono o el usuario pueden estar bajo influencia.

## Dos pistas de trabajo

| Pista | Pregunta | Entorno permitido | Resultado válido |
| --- | --- | --- | --- |
| **Research** | ¿Esta señal aporta información para distinguir o descartar una hipótesis? | Cronologías sintéticas, teléfonos de prueba y cuentas ficticias. | Evidencia de valor, límite o imposibilidad de la señal. |
| **Deployment** | ¿Debería convertirse en una función para personas reales? | Señales mínimas, compatibles con plataforma y sin contenido sensible. | Propuesta con límites, modo de falla e intervención proporcional. |

Una prueba en laboratorio nunca equivale, por sí sola, a una función segura o distribuible.

## Qué contiene este repositorio

| Archivo | Para qué sirve |
| --- | --- |
| [challenge.md](challenge.md) | Define el objetivo, las dos pistas y los criterios de éxito. |
| [threat-model.md](threat-model.md) | Explicita activos, capacidades del atacante y límites de confianza. |
| [scenarios.md](scenarios.md) | Escenarios sintéticos con observaciones y ground truth separados. |
| [proposal-template.md](proposal-template.md) | Formato obligatorio para una propuesta. |
| [example-proposal.md](example-proposal.md) | Ejemplo de Research: una secuencia indistinguible no autoriza una certeza. |
| [scorecard.md](scorecard.md) | Gates de seguridad y rúbrica de evaluación. |
| [CONTRIBUTING.md](CONTRIBUTING.md) | Reglas de colaboración y seguridad pública. |

## Cómo contribuir

1. Leé [challenge.md](challenge.md), [threat-model.md](threat-model.md) y [scenarios.md](scenarios.md).
2. Revisá [example-proposal.md](example-proposal.md) para conocer el nivel de evidencia e incertidumbre esperado.
3. Elegí la pista **Research** o **Deployment**.
4. Completá [proposal-template.md](proposal-template.md).
5. Declarar con precisión qué observás, qué inferís y qué no podés saber.
6. Probá la propuesta contra todos los escenarios, incluyendo los pares benignos cercanos.
7. Respetá [CONTRIBUTING.md](CONTRIBUTING.md): sólo evidencia resumida y material sintético o rigurosamente anonimizado.

## Fuera de alcance por ahora

- Construir una aplicación de monitoreo o vigilancia.
- Probar hipótesis sobre víctimas, teléfonos o cuentas reales.
- Integraciones con bancos, billeteras o proveedores de identidad.
- Leer comunicaciones privadas o códigos.
- Publicar datos personales, activos de fraude o instrucciones operativas de abuso.
- Afirmar cobertura total de estafas móviles.

## Cómo decidimos

Una propuesta primero debe superar los gates de seguridad y método. Sólo después se puntúa de 0 a 20. Una propuesta de Research puede demostrar que una hipótesis es inviable; una propuesta de Deployment además debe explicar una intervención que no dependa únicamente de una decisión manipulable desde el teléfono.

El éxito inicial del repositorio no es una app: es producir conclusiones reproducibles sobre qué se puede observar, qué no se puede distinguir y qué autoridad adicional sería necesaria para intervenir.