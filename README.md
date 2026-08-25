# Mobile Fraud Sequence Challenge

Un desafío abierto y pequeño para encontrar reglas de detección temprana frente a secuencias de toma de control de teléfonos móviles.

> La meta no es prometer que una aplicación "detecta estafas". Es identificar combinaciones observables de eventos que permitan pedir ayuda antes de una acción difícil de revertir.

## El desafío

**¿Qué combinación mínima de eventos permite advertir, con pocas falsas alarmas, que una herramienta de acceso remoto recién instalada está siendo usada para tomar una cuenta o vaciar una billetera?**

El punto de partida son fraudes de ingeniería social en los que una persona es inducida a instalar una herramienta legítima de asistencia remota. A partir de allí, el atacante puede intentar llegar a banca, correo, cuenta Google o WhatsApp.

## Premisas no negociables

- Una aplicación Android convencional tiene límites explícitos: puede correlacionar eventos permitidos y consentidos, pero no conocer de forma fiable el contenido de una llamada de WhatsApp ni lo que ocurre dentro de una cuenta.
- No se recopilan ni procesan mensajes, audio de llamadas, contraseñas, códigos de verificación, capturas de pantalla ni contenido de correo.
- Una señal aislada no prueba una estafa; el objeto de estudio es la **secuencia temporal** y su capacidad de anticipar daño.
- Una alerta útil debe derivar en una acción concreta, idealmente fuera del teléfono potencialmente comprometido.
- Las propuestas se priorizan por evidencia, observabilidad, privacidad y resultados reproducibles; no por popularidad.

## Qué contiene este repositorio

| Archivo | Para qué sirve |
| --- | --- |
| [challenge.md](challenge.md) | Define el único problema inicial y sus límites. |
| [proposal-template.md](proposal-template.md) | Estructura obligatoria para una propuesta. |
| [scenarios.md](scenarios.md) | Cronologías sintéticas de riesgo y uso legítimo. |
| [scorecard.md](scorecard.md) | Criterios y umbral de evaluación. |

## Cómo contribuir

1. Leé el desafío y los escenarios.
2. Planteá una regla o mecanismo de alerta con la plantilla de propuesta.
3. Indicá qué señales son realmente observables en Android normal, qué permisos requiere y qué casos benignos podría confundir.
4. Compará tu propuesta contra todos los escenarios existentes.
5. Abrí un issue o pull request con evidencia verificable y una acción de protección concreta.

Se valoran especialmente aportes de seguridad móvil, Android, prevención de fraude, accesibilidad, UX para personas mayores, privacidad y evaluación de falsos positivos.

## Fuera de alcance por ahora

- Construir la aplicación definitiva.
- Integraciones con bancos, billeteras o proveedores de identidad.
- Escuchar, leer o vigilar comunicaciones privadas.
- Publicar datos reales de víctimas o instrucciones operativas de fraude.
- Resolver todas las modalidades de estafa móvil.

## Cómo decidimos

Cada propuesta se puntúa de 0 a 20. Para ser candidata necesita al menos **14/20**, no depender de datos sensibles y describir una intervención concreta. Los detalles están en [scorecard.md](scorecard.md).

Este repositorio empieza deliberadamente pequeño: una pregunta, pocos escenarios sintéticos y un modo claro de demostrar que una idea mejora lo que ya existe.