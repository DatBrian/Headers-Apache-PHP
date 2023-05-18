# Documentación de headers apache en PHP

En esta documentación encontrarás información detallada acerca de los headers(encabezados) y los ejemplos más comunes para entender su uso, importancia y poder identificarlos.

## ¿Qué es un header?

En Apache con PHP, un header (encabezado) se refiere a la información adicional que se envía desde el servidor web al navegador del cliente antes de enviar los datos de la página. Estos encabezados son parte del protocolo HTTP y se utilizan para transmitir información importante sobre la respuesta del servidor.

Los encabezados se incluyen en la respuesta HTTP y contienen detalles como el tipo de contenido, la codificación de caracteres, la duración de la caché, las cookies, la ubicación de redirección, entre otros. Estos encabezados ayudan al navegador a interpretar correctamente la respuesta y tomar decisiones sobre cómo procesarla.

Para obtener los headers en apache con PHP se utiliza la siguiente función:

```php
apache_request_headers();
```

## Ejemplos de headers

A continuación está la lista de los headers principales que pueden aparecer al ejecutar la función: 

### 1) Host:

El encabezado Host indica el nombre de dominio o la dirección IP del servidor al que se envía la solicitud. Es utilizado por el servidor para determinar a qué dominio o sitio web se está realizando la solicitud. Por ejemplo:

```php
["Host"]=>
string(13) "www.example.com"
```

### 2) Connection:

El encabezado Connection especifica si la conexión debe mantenerse abierta o cerrarse después de completar la respuesta. Puede tener los valores "keep-alive" para mantener la conexión abierta o "close" para cerrarla. Por ejemplo:

```php
["Connection"]=>
string(10) "keep-alive"
```

### 3) Content-Length: 

 El encabezado Content-Length indica la longitud en bytes del cuerpo de la solicitud o de la respuesta. Es utilizado para que el receptor sepa cuántos bytes debe leer del cuerpo del mensaje. Por ejemplo:

```php
["Content-Length"]=>
string(4) "1024"
```

### 4) Sec-Ch-UA:

 Este encabezado es específico de Chrome y se utiliza para indicar información sobre el agente de usuario (user agent) del cliente, como su versión y plataforma. Por ejemplo:

```php
["Sec-Ch-UA"]=>
string(57) ""Google Chrome";v="93", " Not;A Brand";v="99", "Chromium";v="93""
```

### 5) Sec-Ch-UA-Mobile:

Este encabezado es específico de Chrome y se utiliza para indicar si el cliente está en modo móvil o no. Por ejemplo:

```php
["Sec-Ch-UA-Mobile"]=>
string(2) "?0"
```

### 6) Sec-Ch-UA-Platform:

El encabezado `Sec-Ch-Ua-Platform` se utiliza para indicar la plataforma en la que se está ejecutando el agente de usuario (user agent) del cliente que realiza la solicitud. Proporciona información sobre el sistema operativo o plataforma subyacente del dispositivo.

Ejemplo de salida en PHP utilizando `var_dump(apache_request_headers())`:

```php
["Sec-Ch-Ua-Platform"]=>
string(10) "Windows 10"
```



### 7) User-Agent:

El encabezado User-Agent proporciona información sobre el navegador o el agente de usuario que realiza la solicitud. Por ejemplo:

```php
["User-Agent"]=>
string(101) "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/93.0.4577.63 Safari/537.36"
```

### 8) Content-Type:

El encabezado Content-Type indica el tipo de contenido que se envía en la solicitud o en la respuesta. Por ejemplo:

```php
["Content-Type"]=>
string(16) "application/json"
```

### 9) Accept:

El encabezado Accept especifica los tipos de contenido que el cliente está dispuesto a aceptar en la respuesta. Por ejemplo:

```php
["Accept"]=>
string(52) "text/html, application/xhtml+xml, application/xml;q=0.9, */*;q=0.8"
```

### 10) Origin:

El encabezado Origin indica el origen de la solicitud, es decir, el dominio desde el cual se originó la solicitud. Es utilizado en las solicitudes de tipo "Cross-Origin Resource Sharing" (CORS) para determinar si se permite el acceso a recursos desde un dominio diferente. Por ejemplo:

```php
["Origin"]=>
string(23) "https://www.example.com"
```

### 11) Sec-Fetch-Site:

El encabezado `Sec-Fetch-Site` se utiliza para indicar el tipo de sitio de destino de la solicitud. Puede tener los siguientes valores:

- `same-origin`: Indica que el destino de la solicitud es el mismo sitio de origen desde el cual se realizó la solicitud. Esto significa que la solicitud se realiza dentro del mismo dominio.
- `cross-site`: Indica que el destino de la solicitud está en un sitio diferente al sitio de origen. Esto puede ocurrir cuando se realiza una solicitud a través de un dominio diferente, como en el caso de una solicitud de recursos de origen cruzado (CORS).

Un ejemplo de la salida que se obtiene con este encabezado puede ser el siguiente:

```php
["Sec-Fetch-Site"]=>
string(10) "same-origin"
```

### 12) Sec-Fetch-Mode:

El encabezado `Sec-Fetch-Mode` se utiliza para indicar el modo de la solicitud. Puede tener los siguientes valores:

- `navigate`: Indica que la solicitud es una navegación normal del usuario, como hacer clic en un enlace o escribir una URL en la barra de direcciones del navegador.
- `cors`: Indica que la solicitud es una solicitud de recurso de origen cruzado (Cross-Origin Resource Sharing) y está sujeta a restricciones de seguridad CORS.
- `no-cors`: Indica que la solicitud no debe activar una política de CORS y se realiza de forma opaca, sin acceso a la respuesta.

Un ejemplo de la salida que se obtiene con este encabezado puede ser el siguiente:

```php
["Sec-Fetch-Mode"]=>
string(4) "cors"
```

### 13) Sec-Fetch-Dest:

El encabezado `Sec-Fetch-Dest` se utiliza para indicar el destino previsto de la respuesta. Puede tener los siguientes valores:

- `document`: Indica que el destino previsto de la respuesta es un documento HTML o XHTML.
- `image`: Indica que el destino previsto de la respuesta es una imagen.
- `script`: Indica que el destino previsto de la respuesta es un archivo de script, como JavaScript.
- `style`: Indica que el destino previsto de la respuesta es una hoja de estilo CSS.
- `font`: Indica que el destino previsto de la respuesta es una fuente tipográfica.
- `media`: Indica que el destino previsto de la respuesta es un recurso multimedia, como un archivo de audio o video.
- `worker`: Indica que el destino previsto de la respuesta es un trabajador de servicio.
- `sharedworker`: Indica que el destino previsto de la respuesta es un trabajador compartido.
- `embed`: Indica que el destino previsto de la respuesta es un recurso embebido.
- `object`: Indica que el destino previsto de la respuesta es un objeto incrustado.
- `iframe`: Indica que el destino previsto de la respuesta es un iframe.

Un ejemplo de la salida que se obtiene con este encabezado puede ser el siguiente:

```php
["Sec-Fetch-Dest"]=>
string(8) "document"
```

### 14) Referer:

El encabezado Referer (sic) indica la URL de la página desde la cual se realizó la solicitud actual. Este encabezado se utiliza comúnmente para rastrear el origen de los enlaces y proporcionar información al servidor sobre la página desde la cual se hizo clic en un enlace. Por ejemplo:

```php
["Referer"]=>
string(28) "https://www.example.com/page"
```

### 15) Accept-Encoding:

El encabezado Accept-Encoding especifica los algoritmos de compresión que el cliente puede aceptar en la respuesta. Este encabezado se utiliza para indicar al servidor qué métodos de compresión puede utilizar para comprimir el contenido antes de enviarlo al cliente. Los valores comunes para este encabezado incluyen "gzip" y "deflate". Por ejemplo:

```php
["Accept-Encoding"]=>
string(13) "gzip, deflate"
```

### 16) Accept-Language:

El encabezado Accept-Language indica los idiomas preferidos del cliente para la respuesta. Se utiliza para que el servidor pueda enviar una versión localizada de la página si está disponible. Los valores en el encabezado Accept-Language están normalmente en el formato de etiquetas de idioma BCP 47, como "en-US" para inglés estadounidense o "es-ES" para español de España. También se pueden incluir parámetros de calidad (q) para indicar la preferencia relativa de cada idioma. Por ejemplo:

```php
["Accept-Language"]=>
string(14) "en-US,en;q=0.9"
```

