# Evaluación de Riesgos en Arquitectura Híbrida

## 1. Integración y Conectividad

Para garantizar la conectividad estable entre on-premise y cloud. Un fallo en la VPN Gateway podría perder la comunicación, por lo que se recomienda una configuración de alta disponibilidad. Además, la sincronización de datos entre SQL Server on-premise y bases en la nube puede generar inconsistencias. Para evitarlo, se deben implementar verificaciones de integridad, procesos de sincronización automática y monitoreo de latencia.

## 2. Servicios Cloud

Cuando se trabaja con múltiples proveedores como AWS y Azure sube la complejidad de gestionar, para reducir la complejidad se deben considerar herramientas que permitan administrar y monitorear, establecer acuerdos claros, capacitar al equipo, verificar temas de escalabilidad de Kubernetes (EKS), administrar costos y realizar pruebas cada cierto tiempo.  

## 3. Almacenamiento y Seguridad de Datos

Manejar almacenamiento en S3 y Azure Blob puede ser complicado. Para evitar problemas, es importante definir reglas de uso, automatizar la gestión del ciclo de vida y monitorear costos. En cuanto a la seguridad, la exposición de datos sensibles es una preocupación crítica. La solución pasa por rotar credenciales automáticamente, realizar auditorías constantes y aplicar encriptación end-to-end.  

## 4. Servicios de Colas SQS

Los sistemas de mensajería como SQS presentan riesgos como la pérdida de mensajes o procesamiento duplicado. Se pueden mitigar con Dead Letter Queues, monitoreo y estrategias de retry. Por otro lado, las funciones Lambda pueden enfrentar problemas de rendimiento o timeouts, por lo que se debe optimizar código.

## 5. Continuidad del Negocio

Para minimizar el impacto de desastres, es fundamental realizar pruebas periódicas de recuperación con Azure Site Recovery, mantener documentación actualizada y hacer simulacros de recuperación. Además, contar con monitoreo centralizado y alertas proactivas ayuda a reaccionar a tiempo ante fallos.  

## 6. Escalamiento de Incidentes

Se define una matriz de escalamiento que inicia con el equipo de operaciones cloud, seguido por arquitectos de solución y, si es necesario, los proveedores de servicio (AWS/Azure). En casos críticos, se involucra al comité de crisis. Se escalan incidentes como interrupciones prolongadas de VPN, alta latencia en sincronización de datos o vulnerabilidades de seguridad críticas.  

