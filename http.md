## Protocolo HTTP
    Es en esta parte del documento donde se expondrán varios de las 
    características del protocolo HTTP. Que en lugar de transimitir
    información binaria está vinculado a un formato textual.  

    HTTP hace referencia a las siglas en inglés de Hyper Text
    Transfer Protocol. Es un protocolo a nivel de aplicación. Transmite 
    sobre el protocolo TCP y es empleado para la comunicación cliente-servidor 
    donde se transfiere la información que requiere el navegador para mostrar 
    una página por pantalla. 

> Aunque el ejemplo más sencillo sea el navegador tambien sirve a otro tipo de 
> aplicaciones y programas.

    Por lo general se emiten dos grupos de datos. El propio 
    contenido (que no es necesariamente hypertexto) y los 
    metadatos contenidos en la cabecera.
    
> Lo primero que se nos viene a la cabeza con este protocolo es
> la petición de doucmentos HTML. 

> Fue diseñado a principìos de los 90 y se caracteriza por ser 
> en gran medida ampliable.


El protocolo HTTP opera usando una serie de mensajes formateados que depende de unas 
estructuras definidas.

En lugar de ser un flujo continuo de datos, en este caso, se emplean comunicaciones mediante 
**petición** y **respuesta**. 

Una petición hace referencia al mensaje que envía el cliente
mientras que los que son emitidos por el servidor se conocen como respuestas.

Los tipos de operaciones HTTP más comunes son:
> También se les conoce como peticiones HTTP, mensajes HTTP o métodos HTTP.

- GET: es una solicitud de datos al servidor.
    > Indica que solicitamos un recurso como HTML, CSS o cualquier otro tipo de archivo.

- POST: es una solicitud para enviar una entidad a un recurso en específico.
    > Se emplea comunmente en los formularios. Causa cambios en el estado.

- PUT: reemplaza las representaciones del recurso con la carga útil.

- DELETE: Borra el recurso especificado.

> Se encuentra una lista más extensa  y detallada en la [página de Mozilla](https://developer.mozilla.org/es/docs/Web/HTTP/Methods)

**Las peticiones** tienen una estructura de mensaje distinta a la de las respuestas. Se componen 
por el tipo de petición, el path o ruta a la que se aplica, la versión del protocolo y luego 
la serie de cabeceras que componen los metadatos del mensaje. Esta última sección se reemplaza
por el cuerpo del mensaje cuando la petición lol requiere (POST, PUT, etc.)

*Tal y como se observa en la imagen siquiente:*
![http request image](HTTP_Request.png "Esquema descriptivo de una petición HTTP")
>>>>>>>>>>>>>>> Esquema descriptivo de una petición HTTP

<br>

Por otro lado **las respuestas** HTTP son compuestas por la versión del protocolo, el código 
de estado, que es seguido por el mensaje de estado y los headers. Opcionalmente se añade el 
recurso que se ha perdido.

Los códigos de estado se resumen en:
- 1xx (Respuesta)
- 2xx (Éxito)
- 3xx (Redirección) 
- 4xx (Error del cliente) (como el 404 -> página no encontrada)
- 5xx (Error del servidor) (como el 503 -> servicio no disponible)

    > todos estos códigos se especifican más aún en sus distintas variantes (101, 102, ...)


*Se puede apreciar mejor la estructura de la respuesta en la siguiente imagen:*
![http response image](HTTP_Response.png "Esquema descriptivo de una respuesta HTTP")
>>>>>>>>>>>>>>> Esquema descriptivo de una respuesta HTTP

<br>

Todos estos aspectos pueden ser apreciados y analizados desde *Wireshark* a modo de paquetes.
Sin embargo en el propio **navegador** también se puede hacer un **análisis de red** de la
comunicación cliente-servidor mediante el protocolo HTTP. 

<br>
<br>

Si hacemos hincapié en el proceso de la comunicación estudiado en la práctica, se puede apreciar que la primera petición realizada es de DNS.

Esto se da debido a que primero debemos solicitar un acceso al servidor DNS que proporciona
una traducción del dominio solicitado.

La traza es la siguiente: 

    PC :arrow_right:PETICIÓN AL DOMINIO:arrow_right:PETICIÓN AL SERVIDOR DNS:arrow_right:RESPUESTA CON IP TRADUCIDA:arrow_right:ACCESO.