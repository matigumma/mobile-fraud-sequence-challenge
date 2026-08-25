# Challenge 001 — Secuencias de acceso remoto con riesgo de fraude

## Objetivo

Proponer una regla, conjunto de reglas o mecanismo de alerta que identifique una secuencia compatible con una toma de control remota de un teléfono **antes** de que se alcance una aplicación financiera, de identidad o de mensajería.

La propuesta debe funcionar, o explicar con honestidad por qué no podría funcionar, en un Android convencional con consentimiento explícito del usuario.

## Pregunta de trabajo

> ¿Qué señales mínimas, permitidas y observables permiten distinguir una escalada de riesgo de un uso legítimo de soporte remoto?

## Contexto

En campañas de ingeniería social documentadas en Argentina, la víctima puede ser inducida a instalar una herramienta legítima de acceso remoto y luego abrir servicios financieros. La investigación también contempla una escalada hacia correo, cuenta Google o WhatsApp, siempre como hipótesis que debe respaldarse con evidencia.

Este desafío no intenta afirmar que toda secuencia de este tipo sea una estafa. Busca diseñar la mejor alerta temprana posible sin caer en vigilancia invasiva.

## Restricciones

- No leer ni almacenar contenido de chats, correos, llamadas, notificaciones, contraseñas o códigos de un solo uso.
- No usar permisos o técnicas incompatibles con una aplicación Android convencional distribuible.
- No requerir control del dispositivo mediante MDM, administración corporativa ni integración bancaria para la primera versión.
- No tratar una app o evento individual como prueba suficiente de fraude.
- No incluir información que facilite perpetrar, escalar o evadir fraudes.

## Entregable de una propuesta

Cada propuesta debe incluir:

1. Una cadena de riesgo y la evidencia que la fundamenta.
2. Las señales observables y las que quedan fuera del alcance.
3. La regla propuesta, sus ventanas de tiempo y el nivel de riesgo esperado.
4. Su comportamiento frente a todos los escenarios sintéticos.
5. Falsos positivos previsibles y cómo reducirlos.
6. Una acción de protección clara para la persona, su contacto de confianza o una institución.
7. Permisos, datos mínimos y riesgos de privacidad.

Usá [proposal-template.md](proposal-template.md) como formato de base.

## Éxito medible

Una propuesta pasa a estado **Candidate** cuando:

- obtiene al menos 14 de 20 puntos en la rúbrica;
- no activa una alerta externa urgente en los escenarios benignos sin justificarlo;
- anticipa una alerta útil en al menos un escenario de riesgo;
- no depende de contenido sensible ni de una capacidad inaccesible para Android normal;
- permite a alguien hacer algo concreto con la alerta.

## Resultado esperado de este primer ciclo

El resultado puede ser una regla viable, una mejora a los escenarios, evidencia de que una hipótesis es inviable o un conjunto de límites técnicos bien documentados. Un resultado negativo también es útil si evita construir una solución que no puede funcionar.