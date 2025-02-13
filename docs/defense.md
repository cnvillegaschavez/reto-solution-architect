## Defensa

### ¿Por qué consideras que tu solución es la mejor que la de otro partner?

* Considero que mi solución se centra en la optimización de costos de los servicios. Un ejemplo de costos bajo es usar SQS para comunicar entre diferentes microservicios en vez de una tecnología completa como Apache Kafka. 
* Aprovechar a lo máximo de cada nube los servicios que ofrecen segun los requeriemtos del software empresarial. Un ejemplo caro es el almacenamiento en Azure Blog storage para guardar objetos de gran tamaño y mayor tiempo.

* La solución esta orientada a que el costo sea menor para la empresa quien pueda optar por esta arquitectura. (Costo Beneficio)

* Abordo tema de seguridad para mantener seguro la información en ambas nubes y los sitemas on-premises.

* Diagramas bajo modelo C4, permitiendo la facilidad de entender tanto para funcionales o técnicos. En la etapa de implementación se puede aborar el nivel 3 y 4 del diagrama y así estará documentada en su totalidad la solución.


### ¿Cuáles son las principales cuestionamientos que has recibido del cliente al mostrar una solución? En base a ello, ¿cómo sustentarías al cliente que esta solución es lo que le genera valor? (Asume las premisas que consideres necesarias)

Asumimos los siguientes preguntas del lado cliente.

#### 1. ¿Por qué migrar a la nube si ya tenemos infraestructura on-premise funcionando?"

Una de las principales razones es reducción de gatos en hardware, en la nube por la mayoría de los servicios planteados se pagará unicamente por lo que se usa.


#### 2. ¿Como garantiza la seguridad de la información sensible en la nube?
Para garantizar la seguridad en la nube se hace uso de unos servicios que maneja encriptación de datos. En este caso puntual estamos planteando usar AWS Secrets manager y Azure Key Vault, estos servicios nos proporciona diferentes funcionalidades como renovación automatica de vigencia de secretos.

#### 3. ¿Por que consideran trabajar incluyendo 2 nubes?

Se plantea usar 2 nubes, para aprovechar las ventas que nos ofrecen; bajo costo por almacenamiento, aprovechar el modelo de pago por uso, reducción de costos de hardware.



#### 4. ¿No sera muy complejo adminsitrar mas de una nube?

Para facilitar la administración de las nubes ya existen herramientas que permiten bajar esa complejidad, ejemplo herramientas de monitoreo, trazabilidad, documentación clara bajo modelo c4.


#### 5. ¿La solución será capaz de cubrir la necesidad del negocio a medida que va creciendo?

Para llegar a cubrir la necesidad de crecimiento del negocio se esta utilizando servicios de la nube que puede escalar de forma sencilla. Ejemplo si el sistema tendra mas usuarios a lo largo de tiempo, con ciertas configuraciones se le incrementa la memoria, espacio de almacenamiento entre diferentes caracteristicas sin afectar la funcionalidad del software.