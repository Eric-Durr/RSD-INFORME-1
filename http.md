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


El protocolo HTTP opera usando una serie de operaciones definidas que pueden o no depender de unos parámetros y que se emplean para hacer consultas al servidor.

En lugar de ser un flujo continuo de datos, en este caso, se emplean comunicaciones mediante 
**petición** y **respuesta**. 

Una petición hace referencia al mensaje que envía el cliente
mientras que los que son emitidos por el servidor se conocen como respuestas.

Los tipos de operaciones HTTP más comunes son:
> También se les conoce como peticiones HTTP, mensajes HTTP o métodos HTTP.

- GET
- POST
- PUT
- DELETE

Las peticiones tienen una estructura de mensaje distinta a la de las respuestas. Se componen 
por el tipo de petición, el path o ruta a la que se aplica, la versión del protocolo y luego 
la serie de cabeceras que componen los metadatos del mensaje.

> Tal y como se observa en la imagen siquiente

![http request image](HTTP_Request.png "Esquema descriptivo de una petición HTTP")
>>>>>>>>>>>>>>> Esquema descriptivo de una petición HTTP

> Se encuentra una lista más extensa en la [página de Network Sorcery](http://www.networksorcery.com/enp/protocol/http.htm)