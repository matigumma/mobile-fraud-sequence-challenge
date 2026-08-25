# Modelo de amenaza y límites de confianza

Este documento define el modelo defensivo del challenge. No es una descripción operativa de fraude ni una guía para replicarlo.

## Activos a proteger

- Fondos y operaciones financieras.
- Cuenta principal de correo o identidad.
- Cuenta de mensajería y red de contactos.
- Capacidad de la persona para recuperar control de sus servicios.
- Privacidad y autonomía de la persona protegida.

## Actores

| Actor | Interés o responsabilidad |
| --- | --- |
| Persona protegida | Conserva autonomía; puede estar bajo presión o engaño. |
| Atacante de ingeniería social | Busca inducir decisiones legítimas en apariencia. |
| Sistema defensor | Observa sólo las señales permitidas por su pista y declara sus límites. |
| Ancla externa | Persona, institución o canal que puede actuar fuera del teléfono, si fue establecido de manera independiente. |

## Capacidades asumidas del atacante

Una propuesta debe asumir que el atacante puede intentar inducir a la persona a:

- instalar o abrir una herramienta legítima;
- otorgar permisos ordinarios o confirmar diálogos;
- ignorar una advertencia o desactivar una función;
- declarar que una sesión es legítima;
- modificar configuraciones disponibles desde el mismo dispositivo;
- esperar, reutilizar software ya instalado o cambiar el orden de una secuencia.

Por lo tanto, una decisión tomada sólo desde el teléfono potencialmente manipulado es una **entrada controlable por el atacante**, no una garantía de seguridad.

## Qué puede observarse y qué no

| Capa | Ejemplo | Regla para las propuestas |
| --- | --- | --- |
| Evento observable | Instalación de un paquete conocido; cambio de aplicación en primer plano. | Puede usarse si se declara el permiso, cobertura y limitación. |
| Inferencia | “Hay asistencia remota activa”; “la persona está siendo engañada”. | Debe etiquetarse como inferencia y expresar incertidumbre. |
| Ground truth de laboratorio | En la simulación hubo una acción de riesgo o una interacción legítima. | Sólo sirve para puntuar, nunca como entrada de la regla. |
| Daño real | Transferencia, toma de cuenta, expulsión de sesión. | No se presume por una cronología de aplicaciones. |

## Principio de independencia

Una alerta dentro del mismo teléfono puede ser útil como fricción, pero no es un ancla de confianza suficiente si el atacante puede persuadir a la persona para descartarla.

Cualquier propuesta que use una persona o canal externo debe explicar:

- cómo se establece esa relación;
- cómo se cambia o revoca;
- si esos cambios pueden hacerse sólo desde el dispositivo vigilado;
- qué exposición de datos recibe el tercero;
- qué ocurre si no responde o no es confiable.

No se asume que “contacto de confianza” sea seguro por definición.

## Límites éticos y de investigación

- El challenge usa solamente datos sintéticos, cuentas ficticias o material rigurosamente anonimizado.
- No se prueban cadenas sobre víctimas ni sobre cuentas reales.
- No se publican códigos, enlaces, credenciales, activos ni instrucciones que incrementen capacidad ofensiva.
- Un consentimiento dado bajo presión, engaño o dentro de la misma sesión no convierte una práctica invasiva en aceptable para Deployment.

## Conclusión aceptable

Una propuesta puede concluir que una secuencia no es distinguible con los eventos disponibles. Esa conclusión debe registrarse como resultado de Research, no corregirse con confianza artificial, vigilancia adicional o una afirmación de certeza.