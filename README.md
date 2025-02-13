# 🌐 Modernización de Infraestructura Tecnológica en Entorno Híbrido

##  Problema a Resolver
La empresa busca modernizar su infraestructura tecnológica actual para **optimizar el procesamiento y almacenamiento de datos** en un entorno híbrido. El objetivo es implementar una solución que permita una **integración continua entre los entornos locales y la nube**, facilitando la comunicación entre sistemas y mejorando la **seguridad, eficiencia y disponibilidad del sistema**.

---

## ⚙️ Requerimientos Técnicos

###  1. Diseño de Arquitectura
- Proponer un diseño que combine servicios en la nube (**Cloud A y Cloud B**) con la infraestructura **on-premises**.
- Incluir mecanismos de orquestación y monitoreo en la nube para gestionar la comunicación entre los sistemas on-premises y cloud.
- Utilizar Kubernetes para la gestión de contenedores y la orquestación de microservicios en la nube.

###  2. Integración de Sistemas
- Definir una estrategia de integración que optimice la comunicación entre los servicios backend en servidores locales y los servicios en la nube (por ejemplo, funciones serverless o contenedores en Kubernetes).
- Proponer un flujo de mensajes asíncronos para la comunicación entre los sistemas.

###  3. Estrategia de Almacenamiento
- Diseñar una solución de almacenamiento distribuido para gestionar grandes volúmenes de datos, asegurando la consistencia y seguridad de los mismos.
- Proponer una estrategia de migración de datos desde la infraestructura local a un sistema de almacenamiento distribuido en la nube.

###  4. Escalabilidad y Resiliencia
- Proponer una solución capaz de escalar dinámicamente en función de la carga de trabajo.
- Definir estrategias de recuperación ante desastres para asegurar la continuidad del negocio.

###  5. Seguridad y Gobernanza
- Asegurar que la solución propuesta cumpla con los requisitos de seguridad mediante el uso de tecnologías de gestión de secretos y certificados.
- Proponer un plan de gobernanza para la gestión de accesos y permisos en el entorno híbrido.


--
## Descripción
Este repositorio contiene la solución propuesta para la modernización de infraestructura tecnológica de una empresa con integración entre sistemas on-premise y la nube.

### 📂 Entregables
✅ [Diagrama de Arquitectura](docs/diagram-architecture.md) (Click para ver respuesta)
- Un diagrama detallado que muestre la arquitectura propuesta, incluyendo los componentes locales y en la nube, así como sus interacciones.

✅ [Documentación Técnica](docs/documentation-tech.md)  (Click para ver respuesta)
- Descripción de cada componente del sistema, su funcionalidad y cómo se integran entre sí.
- Justificación técnica de las decisiones arquitectónicas tomadas.

✅ [Plan de Implementación](docs/implementation.md) (Click para ver respuesta)
- Plan de implementación detallado que describa cómo se llevará a cabo la integración y migración de los sistemas actuales a la nueva arquitectura.
- Estrategia de pruebas y validación de la solución.

✅ [Evaluación de Riesgos](docs/danger.md) (Click para ver respuesta)
- Identificación de posibles riesgos durante la implementación y medidas de mitigación para reducir su impacto.

✅ [Defensa de la Solución](docs/defense.md) (Click para ver respuesta)
- ¿Por qué consideras que tu solución es la mejor que la de otro partner? 
- ¿Cuáles son las principales cuestionamientos que has recibido del cliente al mostrar una solución? En base a ello, ¿cómo sustentarías al cliente que esta solución es lo que le genera valor? (Asume las premisas que consideres necesarias)
