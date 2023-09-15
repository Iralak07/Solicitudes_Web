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


  






