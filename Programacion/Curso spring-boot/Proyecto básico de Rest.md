¿Qué es Rest?
**REST (Representational State Transfer)**
Arquitectura de software para diseñar sistemas distribuidos, como APIs web.

REST se basa en un conjunto de principios y restricciones que permiten la creación de sistemas escalables, sencillos y eficientes.

Las APIs RESTful son populares debido a su simplicidad y uso de estándares ampliamente adoptados como HTTP.



#### **Características Clave de REST:**

- **Cliente-Servidor:** REST separa las responsabilidades entre el cliente y el servidor. El cliente realiza solicitudes, mientras que el servidor gestiona los recursos y devuelve respuestas.
- **Sin Estado (Stateless):** Cada solicitud desde el cliente al servidor debe contener toda la información necesaria para que el servidor procese la solicitud. El servidor no guarda estado del cliente entre solicitudes.
- **Cacheable:** Las respuestas de los recursos pueden ser cacheadas, lo que mejora el rendimiento al evitar solicitudes repetidas.
- **Interfaz Uniforme:** REST utiliza una interfaz uniforme, normalmente basada en operaciones HTTP estándar (GET, POST, PUT, DELETE), para interactuar con los recursos.
- **Uso de Recursos:** En REST, cada elemento de datos (por ejemplo, un usuario, producto, etc.) es tratado como un “recurso”. Estos recursos se identifican mediante una URI (Uniform Resource Identifier).
- **Representaciones de Recursos:** Los recursos pueden ser representados en diferentes formatos como JSON, XML, HTML, etc., pero el formato más común en las APIs RESTful modernas es JSON.



---
#### **Operaciones CRUD con REST y HTTP:**

En una API RESTful, las operaciones CRUD (Crear, Leer, Actualizar, Eliminar) se mapearían a los métodos HTTP de la siguiente manera:

- **GET:** Obtener o leer un recurso.
    - Ejemplo: `GET /usuarios/1` (Obtiene los detalles del usuario con ID 1).
- **POST:** Crear un nuevo recurso.
    - Ejemplo: `POST /usuarios` (Crea un nuevo usuario).
- **PUT:** Actualizar un recurso existente.
    - Ejemplo: `PUT /usuarios/1` (Actualiza los detalles del usuario con ID 1).
- **DELETE:** Eliminar un recurso.
    - Ejemplo: `DELETE /usuarios/1` (Elimina el usuario con ID 1).



---
### Clientes para realizar peticiones REST

#### **Postman**

- **Descripción**: Postman es una de las herramientas más populares para probar y desarrollar APIs REST. Ofrece una interfaz gráfica completa para realizar, organizar y automatizar peticiones.
- **Web**: [https://www.postman.com/](https://www.postman.com/)

#### **Insomnia**

- **Descripción**: Insomnia es una aplicación ligera y fácil de usar para pruebas de APIs REST y GraphQL. Es conocida por su interfaz limpia y su simplicidad para gestionar variables y entornos.
- **Web**: [https://insomnia.rest/](https://insomnia.rest/)

#### S**oapUI**:

- **Descripción**: SoapUI es una herramienta de pruebas de APIs, especialmente orientada a servicios SOAP, pero también compatible con REST. Ofrece funcionalidades avanzadas para automatizar pruebas.
- **Web**: [https://www.soapui.org/](https://www.soapui.org/)

#### **Yaak**

- **Descripción**: Yaak es una herramienta nueva y ligera para pruebas de APIs REST. Se enfoca en la simplicidad y la automatización, permitiendo organizar, reutilizar y compartir peticiones de manera eficiente. Aunque no es tan conocida como Postman o Insomnia, Yaak es una buena opción para quienes buscan una alternativa moderna y minimalista para gestionar sus pruebas de APIs.
- **Web**: [https://yaak.dev/](https://yaak.dev/)

#### Cartero

- **Descripción**: Cartero es un cliente HTTP gráfico que se puede utilizar como herramienta de desarrollo para probar API web y realizar todo tipo de solicitudes HTTP a servidores web. Es compatible con cualquier API REST, SOAP o XML-RPC y admite múltiples métodos de solicitud, además de adjuntar cargas útiles a solicitudes compatibles.
- **Web**: [https://github.com/danirod/cartero](https://yaak.dev/)

-------------
