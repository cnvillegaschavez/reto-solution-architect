# 🏗 Documentación técnica

Esta arquitectura híbrida combina sistemas on-premise con servicios en la nube de **AWS y Azure**, aprovechando lo mejor de cada plataforma para ofrecer una infraestructura **escalable, segura y optimizada en costos**.

## 💻 On-premise

### Backend Services

Los servicios empresariales existentes en **Java y .NET** siguen manejando la lógica de negocio principal y el procesamiento de transacciones locales.

Puntos clave:
* Mantener compatibilidad con los sistemas legacy
* Asegurar comunicación segura con la nube
* Optimizar la latencia de las conexiones
* El servicio backend realiza conexión a la base de datos SQL


### Base de Datos (SQL Server)

El almacenamiento transaccional sigue en **SQL Server**, con estrategias de **replicación y respaldo**.

Consideraciones:
* **Sincronización con bases de datos en la nube** (Amazon RDS y DynamoDB)
* **Estrategia de backup y recuperación ante desastres**
* **Optimización de consultas** para mejorar el rendimiento
* La base de datos es consumida por el servicio backend

### VPN Gateway

Para la conexión segura entre on-premise y la nube, utilizamos un **VPN Gateway Site-to-Site**, con:
* Alta disponibilidad
* Monitoreo de conexión
* Encriptación de datos en tránsito
* El VPN enruta trafico al API Gateway del Cloud

## ☁️ Cloud AWS

### Amazon S3 (Almacenamiento de Objetos)

Utilizamos **Amazon S3** para almacenar archivos y datos no estructurados, con diferentes niveles de acceso:

* **Standard**: Para acceso frecuente
* **Intelligent-Tiering**: Para optimizar costos automáticamente
* **Glacier**: Para almacenamiento a largo plazo
* Los objetos procesados por lambda function son almacenado o recuperados del S3

Características:
* **Encriptación en reposo y en tránsito**
* **Versionado y control de accesos** con IAM
* **Lifecycle Management** para migración automática entre niveles

### Amazon RDS (Base de Datos Relacional en la Nube)

Para manejar datos transaccionales en la nube, utilizamos **Amazon RDS PostgreSQL**.

Beneficios:
* **Administración automática** de backups y parches
* **Escalabilidad vertical y horizontal**
* **Replicación entre regiones** para alta disponibilidad
* Los datos son escritos o recuperados desde lambdas funcions o micro servicios alojados en 

### Amazon DynamoDB (Base de Datos NoSQL)

Para almacenar datos **NoSQL de alto rendimiento**, implementamos **DynamoDB**, ideal para consultas rápidas y escalabilidad automática.

* **Gestión de sesiones de usuarios**
* **Almacenamiento de eventos en tiempo real**
* **Datos con acceso frecuente y latencia baja**
* Los datos son escritos o recuperados desde lambdas funcions o micro servicios alojados en 

### API Gateway

Facilita la gestión de APIs proporcionando:
* Punto de entrada unificado para microservicios
* Autenticación y control de tráfico
* **Caché de respuestas** para mejorar el rendimiento
* Punto de integración con el VPN de On-primise

### Kubernetes (EKS)

Para la orquestación de contenedores, usamos **Amazon EKS**, con:
* **Auto-scaling y balanceo de carga**
* **Istio Service Mesh** para mejorar la comunicación entre microservicios
* **Monitoreo con CloudWatch**
* Se plantea el uso de Kubernetes para procesos pesados

### Serverless Functions (AWS Lambda)
AWS Lambda permite ejecutar funciones sin gestionar servidores, con:
* **Escalado automático**
* **Modelo de pago por uso**
* **Integraciones con eventos de S3, DynamoDB y API Gateway**
* Se plantea el uso de Lambdas para procesos menos pesados

### Mensajería Asíncrona (SQS)

Implementamos **SQS** para comunicación asíncrona y desacoplamiento de servicios:
* **Colas FIFO**
* **Entrega garantizada y ordenada**
* **Filtrado de mensajes y Dead Letter Queues**
* Manejo de colas de mensajes y bajo costo comparando con otras herramientas como Kafka.

### Gestión de Secretos (Secrets Manager)

AWS Secrets Manager permite:
* **Rotación automática de credenciales**
* **Integración con IAM y bases de datos**
* **Encriptación en reposo con auditoría de accesos**
* Con el fin de guardar datos sensibles, ejemplo de variables de entorno, conexiones a bases de datos. 

## ☁️ Cloud Azure

### Azure Blob Storage

Para almacenamiento de objetos en Azure, con niveles:
* **Hot**: Acceso frecuente
* **Cool**: Acceso infrecuente
* **Archive**: Almacenamiento a largo plazo

Características:
* Redundancia geográfica
* Control de acceso granular
* Encriptación automática
* Costo bajo

### Azure Site Recovery (Disaster Recovery)

Para la continuidad del negocio, **Azure Site Recovery** ofrece:
* **Replicación asíncrona de datos**
* **Orquestación automatizada de recuperación**
* **Pruebas de failover sin afectar la producción**

### Azure Key Vault

Para la seguridad de credenciales y certificados, **Azure Key Vault** proporciona:
* **Almacenamiento seguro de secretos**
* **Gestión de certificados**
* **Integración con servicios de Azure**
* Con el fin de guardar datos sensibles, ejemplo de variables de entorno, conexiones a bases de datos. 

----
# 🤔 Justificación Técnica

### Kubernetes (EKS) en AWS

Implementamos Kubernetes porque ofrece:
* **Orquestación automatizada y escalabilidad horizontal**
* **Alta disponibilidad y balanceo de carga**
* **Facilidad de integración con servicios AWS**

### Amazon S3 + Azure Blob Storage

La combinación de estos dos servicios permite:
* **Alta disponibilidad y redundancia geográfica**
* **Optimización de costos con storage tiering**
* **Escalabilidad para grandes volúmenes de datos**

### Bases de Datos Mixtas (SQL Server, RDS y DynamoDB)

Esta arquitectura combina **bases de datos relacionales y NoSQL** para optimizar la gestión de datos:
* **SQL Server On-Premise + RDS**: Datos estructurados y transaccionales
* **DynamoDB**: Datos altamente distribuidos con acceso en tiempo real

### Mensajería Asíncrona con SQS

Beneficios:
* **Desacoplamiento de servicios**
* **Mayor resiliencia y tolerancia a fallos**
* **Manejo eficiente de picos de carga**
* Comunicacion entre micro servicios mediante eventos y subscripciones.

-----
✅ [Plan de Implementación](implementation.md) (Click para ver respuesta)