# Solicitudes_Web

Las solicitudes web (web request) son fundamentales para la comunicación entre cliente y servidor 

Una solicitud web, se realiza principalmente a travez el protocolo HTTP (Hypertext Transfer Protocol). La mayoría de las comunicaciones por Internet se realizan con solicitudes web a través del protocolo HTTP. 

`#`Ques es el protocolo HTTP?

  Es un protocolo de nivel de aplicación utilizado para acceder a los recursos de la World Wide Web. El término significa texto que contiene enlaces a otros recursos y texto que los lectores pueden interpretar fácilmente (hypertext). La comunicación HTTP consiste en un cliente y un servidor, donde el cliente solicita al servidor un recurso. El servidor procesa las solicitudes y devuelve el recurso solicitado.
  
   A fin de acceder a esos recursos a traves del protocolo HTTP, es utilizada la URL, que ofrece muchas más especificaciones que simplemente especificar un sitio web que queremos visitar. URL significa Uniform Resource Locator (Localizador de Recursos Uniforme). Una URL no es más que una direccion que es dada a un recurso único en la Web. En teoria, cada URL válida apunta a un único recurso. Dichos recursos pueden ser páginas HTML, documentos CSS, imagenes, etc.

   La estructura de URL se ve de la siguiente manera:

![estructuraURL](https://github.com/Iralak07/Solicitudes_Web/assets/99599597/f18174e7-467f-4cee-9e10-9229313db168)


  Scheme: Esto se utiliza para identificar el protocolo al que accede el cliente, y termina con dos puntos y una barra diagonal doble, el protocolo puede ser http como https. 
  
  User Info: Se trata de un componente opcional que contiene las credenciales (separadas por dos puntos) utilizadas para autenticarse en el host y está separado del host con un signo arroba, (admin:password@)

  Host: inlanefreight.com, el host significa la ubicación del recurso. Puede ser un nombre de host o una dirección IP

  Port: El está separado del por dos puntos (:). Si no se especifica el puerto, este se ubica en el puerto predeterminado ya sea el puerto 80 o el 443.

  Path: Esto apunta al recurso al que se está accediendo, que puede ser un archivo o una carpeta. Si no hay ninguna ruta especificada, el servidor devuelve el índice predeterminado. Un ejemplo es la pagina index.html

  Query String: La cadena de consulta comienza con un signo de interrogación (?login=true), y consta de un parámetro  y un valor. Se pueden separar varios parámetros mediante un signo (?logintrue&).Es importante mencionar que la cadena de consulta es opcional en una URL, y no todas las URL la contienen. Cuando no se necesita pasar parámetros adicionales, simplemente se omite y la URL se limita a la dirección base.

  Fragments: Los fragmentos son procesados por los navegadores en el lado del cliente para localizar secciones dentro del recurso principal (por ejemplo, un encabezado o sección en la página).

`#` Protocolo seguro de transferencia de hipertexto (HTTPS)

Antes que nada, veremos cómo se envían y procesan las solicitudes HTTP. Sin embargo, uno de los inconvenientes importantes de HTTP es que todos los datos se transfieren en texto no cifrado. Esto significa que cualquier persona entre el origen y el destino puede realizar un ataque Man-in-the-middle (MiTM) para ver los datos transferidos.

Para contrarrestar este problema, se creó el protocolo HTTPS (HTTP Secure), en el que todas las comunicaciones se transfieren en un formato cifrado, por lo que incluso si un tercero intercepta la solicitud, no podría extraer los datos de ella. Por esta razón, HTTPS se ha convertido en el esquema principal para sitios web en Internet, y HTTP se está eliminando gradualmente, y pronto la mayoría de los navegadores web no permitirán visitar sitios web HTTP.

Los sitios web que aplican HTTPS se pueden identificar a través de su URL (por ejemplo, https://www.google.com), así como el icono de candado en la barra de direcciones del navegador web, a la izquierda de la URL: https://

`#` Solicitudes y respuestas HTTP (request and response)

Las comunicaciones HTTP consisten principalmente en una solicitud HTTP y una respuesta HTTP. Una solicitud HTTP es realizada por el cliente (navegador) y es procesada por el servidor (por ejemplo, servidor web). Las solicitudes contienen todos los detalles que requerimos del servidor, incluido el recurso (por ejemplo, URL, ruta, parámetros), cualquier dato de solicitud, encabezados u opciones que especifiquemos, y muchas otras opciones. 

Una vez que el servidor recibe la solicitud HTTP, la procesa y responde enviando la respuesta HTTP, que contiene el código de respuesta. 

`#` Solicitud HTTP

![raw_request](https://github.com/Iralak07/Solicitudes_Web/assets/99599597/99a7dc46-108a-4ba9-84e0-182eacd62abd)

La primera línea de cualquier solicitud HTTP contiene tres campos principales "separados por espacios":

Metodo: El método HTTP o verbo, que especifica el tipo de acción que se va a realizar.

Path:	La ruta de acceso al recurso al que se tiene acceso. Este campo también se puede sufijar con una cadena de consulta (por ejemplo, /users/login.html?username=user).

Version: 	El tercer y último campo se utiliza para indicar la versión HTTP (HTTP/1.1).  HTTP versión 1.X envía solicitudes como texto no cifrado y utiliza un carácter de nueva línea para separar diferentes campos y diferentes solicitudes. HTTP versión 2.X, por otro lado, envía solicitudes como datos binarios en forma de diccionario.
  
El siguiente conjunto de líneas contiene pares de valores de encabezado HTTP,  y muchos otros encabezados posibles. Estos encabezados se utilizan para especificar varios atributos de una solicitud. Los encabezados terminan con una nueva línea, que es necesaria para que el servidor valide la solicitud. Finalmente, una solicitud puede terminar con el cuerpo y los datos de la solicitud.

`#` Respuesta HTTP

Una vez que el servidor procesa la solicitud, envía su respuesta. A continuación se muestra un ejemplo de respuesta HTTP:

![raw_response](https://github.com/Iralak07/Solicitudes_Web/assets/99599597/bc285600-a1a8-48ed-8492-e6a6b236ada0)

La primera línea de una respuesta HTTP contiene dos campos separados por espacios. El primero es la version, y el segundo denota el codigo de respuesta. Los códigos de respuesta se utilizan para determinar el estado de la solicitud, en la siguiente direccion pueden acceder a todos los codigos de respuestas utilizados (https://developer.mozilla.org/es/docs/Web/HTTP/Status). 

Finalmente, la respuesta puede terminar con un cuerpo de respuesta, que está separado por una nueva línea después de los encabezados. El cuerpo de respuesta generalmente se define como código. Sin embargo, también puede responder con otros tipos de código, como recursos del sitio web, como imágenes, hojas de estilo o scripts, o incluso un documento como un documento PDF alojado en el servidor web.

`#` Encabezados HTTP

Los encabezados HTTP pasan información entre el cliente y el servidor. Algunos encabezados solo se usan con solicitudes o respuestas, mientras que otros encabezados generales son comunes a ambos.

Los encabezados pueden tener uno o varios valores, anexados después del nombre del encabezado y separados por dos puntos. Podemos dividir los encabezados en las siguientes categorías:

-  General Headers
-  Entity Headers
-  Request Headers
-  Response Headers
-  Security Headers

Analicemos cada una de estas categorías.

## General Headers [Encabezados Generales](https://www.w3.org/Protocols/rfc2616/rfc2616-sec4.html)

Los encabezados generales se utilizan tanto en las solicitudes como en las respuestas HTTP. Son contextuales y están acostumbrados a contener una descripcion del mensaje.

## Entity headers (Encabezados de entidad)

 Los mensajes de solicitud y respuesta PUEDEN transferir una entidad si no es de otra manera Restringido por el método de solicitud o el código de estado de respuesta. Una entidad consta de campos de encabezado de entidad y un cuerpo de entidad, aunque algunos Las respuestas solo incluirán los encabezados de entidad.
 
  Los campos de encabezado de entidad definen la metainformación sobre el cuerpo de entidad o, si no hay ningún cuerpo presente, sobre el recurso identificado por la solicitud. Parte de esta metainformación es OPCIONAL; algunos podrían ser REQUERIDOS por partes de esta especificación.

       entity-header  = Allow                    
                      | Content-Encoding         
                      | Content-Language         
                      | Content-Length           
                      | Content-Location         
                      | Content-MD5              
                      | Content-Range           
                      | Content-Type             
                      | Expires                 
                      | Last-Modified            
                      | extension-header

  
## Request headers (Encabezados de solicitud)

  El cliente envía encabezados de solicitud en una transacción HTTP. Los siguientes encabezados se ven comúnmente en las solicitudes HTTP.

    - Host: Se utiliza para especificar el host que se consulta para el recurso. Puede ser un nombre de dominio o una dirección IP. Los servidores HTTP se pueden configurar para alojar diferentes sitios web, que se revelan en función del nombre de host. Esto hace que el encabezado de host sea un destino de enumeración importante, ya que puede indicar la existencia de otros hosts en el servidor de destino.

    - User-Agent: El encabezado se utiliza para describir el cliente que solicita recursos. Este encabezado puede revelar mucho sobre el cliente, como el navegador, su versión y el sistema operativo.

    - Referer: Indica de dónde proviene la solicitud actual. Por ejemplo, hacer clic en un enlace de los resultados de búsqueda de Google haría la referencia. Confiar en este encabezado puede ser peligroso, ya que puede manipularse fácilmente, lo que lleva a consecuencias no deseadas.
  
    - Accept	El encabezado describe qué tipos de medios puede entender el cliente. Puede contener varios tipos de medios separados por comas. El valor significa que se aceptan todos los tipos de medios.Accept */*

    - Cookie: PHPSESSID=b4e4fbd93540, 	Contiene pares cookie-value en el formato . Una cookie es un dato almacenado en el lado del cliente y en el servidor, que actúa como un identificador. Estos se pasan al servidor por solicitud, manteniendo así el acceso del cliente. Las cookies también pueden servir para otros propósitos, como guardar las preferencias del usuario o el seguimiento de la sesión. Puede haber varias cookies en un solo encabezado separadas por un punto y coma. Cookie: cookie1=valor1; cookie2=valor2; cookie3=valor3

    - Authorization: BASIC cGFzc3dvcmQK, Otro método para que el servidor identifique a los clientes. Después de una autenticación correcta, el servidor devuelve un token único para el cliente. A diferencia de las cookies, los tokens se almacenan solo en el lado del cliente y el servidor los recupera por solicitud. Existen varios tipos de autenticación basados en el servidor web y el tipo de aplicación utilizados.

## Response Headers (Encabezados de respuesta)

Los encabezados de respuesta se utilizan para proporcionar más contexto sobre la respuesta. Los siguientes encabezados se ven comúnmente en las respuestas HTTP.

  - Server: Apache/2.2.14 (Win32)	Contiene información sobre el servidor HTTP que procesó la solicitud. Se puede utilizar para obtener información sobre el servidor, como su versión, y enumerarla más.

  - Set-Cookie: PHPSESSID=b4e4fbd93540	Contiene las cookies necesarias para la identificación del cliente. Los navegadores analizan las cookies y las almacenan para futuras solicitudes. Este encabezado sigue el mismo formato que el encabezado de solicitud.Cookie

  - WWW-Authenticate: BASIC realm="localhost"	Notifica al cliente sobre el tipo de autenticación necesaria para tener acceso al recurso solicitado.

## Security Headers (Encabezados de seguridad)

Por último, tenemos los encabezados de seguridad. Con el aumento de la variedad de navegadores y ataques basados en la web, era necesario definir ciertos encabezados que mejoraran la seguridad. Los encabezados de seguridad HTTP deben ser seguidos por el navegador mientras se accede al sitio web. 


# Métodos y códigos HTTP

TTP admite varios métodos para acceder a un recurso. En el protocolo HTTP, varios métodos de solicitud permiten al explorador enviar información, formularios o archivos al servidor. Estos métodos se utilizan, entre otras cosas, para decirle al servidor cómo procesar la solicitud que enviamos y cómo responder.

## Métodos de solicitud

  - Metodo "GET":	Solicita un recurso específico. Se pueden pasar datos adicionales al servidor a través de cadenas de consulta en la URL (http://ejemplo.com/recurso?nombre=Juan&edad=30)

  - Metodo "POST": Envía datos al servidor. Puede manejar múltiples tipos de entrada, como texto, PDF y otras formas de datos binarios. Estos datos se anexan en el cuerpo de la solicitud presente después de los encabezados. El método POST se usa comúnmente cuando se envía información (por ejemplo, formularios / inicios de sesión) o se cargan datos en un sitio web, como imágenes o documentos.

  - Metodo "HEAD": Solicita los encabezados que se devolverían si se realizara una solicitud GET al servidor. No devuelve el cuerpo de la solicitud y generalmente se realiza para verificar la longitud de la respuesta antes de descargar recursos.

  - Metodo "PUT": Crea nuevos recursos en el servidor. Permitir este método sin los controles adecuados puede llevar a la carga de recursos maliciosos.

  - Metodo "DELETE": Elimina un recurso existente en el servidor web. Si no se protege adecuadamente, puede conducir a la denegación de servicio (DoS) mediante la eliminación de archivos críticos en el servidor web.

  - Metodo "OPTIONS": Devuelve información sobre el servidor, como los métodos aceptados por él.

## Códigos de respuesta

Los códigos de estado HTTP se utilizan para indicar al cliente el estado de su solicitud. Un servidor HTTP puede devolver cinco tipos de códigos de respuesta:

Tipo	Descripción
- 1xx	Proporciona información y no afecta al procesamiento de la solicitud.
- 2xx	Se devuelve cuando una solicitud se realiza correctamente.
- 3xx	Se devuelve cuando el servidor redirige al cliente.
- 4xx	Significa solicitudes incorrectas. Por ejemplo, solicitar un recurso que no existe o solicitar un formato incorrecto.from the client
- 5xx	Devuelto cuando hay algún problema en sí.with the HTTP server
- 
Los siguientes son algunos de los ejemplos más comunes de cada uno de los tipos de método HTTP anteriores:

Código	                    Descripción
- 200 OK	                  Se devuelve en una solicitud correcta y el cuerpo de respuesta suele contener el recurso solicitado.
- 302 Found	                Redirige al cliente a otra URL. Por ejemplo, redirigir al usuario a su panel después de un inicio de sesión exitoso.
- 400 Bad Request	          Se devuelve al encontrar solicitudes con formato incorrecto, como solicitudes con terminadores de línea faltantes.
- 403 Forbidden	            Significa que el cliente no tiene acceso adecuado al recurso. También se puede devolver cuando el servidor detecta entradas maliciosas del usuario.
- 404 Not Found	            Se devuelve cuando el cliente solicita un recurso que no existe en el servidor.
- 500 Internal Server Error	Se devuelve cuando el servidor no puede procesar la solicitud.


