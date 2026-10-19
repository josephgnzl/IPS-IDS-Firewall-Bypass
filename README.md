# ¿Qué es un firewall?

Un firewall es un control de seguridad que aplica políticas sobre el tráfico de red para determinar qué comunicaciones se permiten, se bloquean o se inspeccionan. Su comportamiento depende de las reglas configuradas, el contexto de la conexión y las capacidades de inspección implementadas.

## ¿Cómo Funcionan?

Un firewall funciona como un punto de control del tráfico de red: recibe o inspecciona paquetes, evalúa las reglas de seguridad aplicables y determina si permite, bloquea o somete la comunicación a inspecciones adicionales.


## Tipos de Firewalls

| Tipo | Mecanismo principal |
|---|---|
| Stateless | Filtrado individual de paquetes mediante reglas. |
| Stateful | Seguimiento del estado de las conexiones. |
| Proxy / Application Gateway | Intermediación e inspección de comunicaciones a nivel de aplicación. |
| Next-Generation Firewall (NGFW) | Integración de inspección de aplicaciones, identificación de amenazas y otras funciones avanzadas. |

## Firewall desde la perspectiva de Red Team

Durante el reconocimiento, el firewall condiciona qué información puede obtenerse desde una posición determinada. Las respuestas de los objetivos, los tiempos de espera y la ausencia de respuesta pueden aportar indicios sobre las políticas de filtrado, pero no permiten determinar por sí solos la configuración exacta del dispositivo.
