## Protocolo Ethernet y ARP
    En este apartado se hablará sobre los protocolos Ethernet
    y ARP. Se entrará en detalles sobre sus cabeceras y funcionamiento. 
    


![Eth portada](ethernet.png "cable ethernet a modo de portada")
>>>>>>>>>>>>>>>Imagen del cable RJ45, icono de este protocolo 


### PROTOCOLO ETHERNET

**Antecedentes:**
> El protocolo Ethernet tiene como precursor al protocolo ALOHA
> siendo este una mejora basada en muchos de los conceptos del
> protocolo anterior.

> Este protocolo es el más usado para areas locales, cableadas,
> a nivel de enlace. Permite el acceso múltiple y consta de un
> esquema que le permite evitar colisiones.

> Al estar a nivel de enlace se habla de una "trama" cuando nos 
> referimos al paquete enviado. Esta es una traducción directa 
> del mensaje en bits de la capa física y una encapsulación del
> datagrama de la capa de red, que es su superior.

**Estructura del marco Ethernet**
> La trama Ethernet se compone por una carga útil; que es el
> datagrama, ya encapsulado, de la capa superior y por una 
> cabecera Ethernet; que continene información relativa al 
> direccionamiento, control, uso y comprobación de la 
> comunicación.

> Por lo general se  estructura en varias subcapas.

> El estudio de este protocolo durante la práctica no ha 
> profundizado en cuestiones demasiado concretas. Los aspectos
> que se presentan son en su mayoría básicos. 


![Eth TRAMA](Trama.png "Imagen de la trama ethernet")
>>>>>>>>>>>>>>>Imagen que expresa la trama ethernet.


Dependiendo del estandar de Ethernet empleado el marco puede variar,
durante el curso ampliaremos el caso del estandar IEEE 802.3.Algunos 
elementos más generales pueden ser similares entre varios de estos. 
Por ejemplo en *Wireshark* se muestran los iguientes:

- Destino
- Origen 
- tipo (*Frame type*)

Estos datos permiten conocer las direcciones MAC de los dispositivos 
interconectados en la misma red cableada. De esta manera se conoce el
**origen** y el **destino** en una comunicación. Expresados bajo los campos
del marco que indican esto.

Un ejemplo de este caso se produce en las **peticiones GET** a una 
página web. Donde el dispositivo origen solicita una serie de datos 
al dispositivo destino, que es el servidor donde se encuentra alojada.

Eventualmente el servidor contestará con una respuesta, es en este punto
donde se intercambian los roles en cuanto a destinatario y origen. Este
efecto se puede estudiar y visualizar mediante el marco del protocolo
Ethernet.

Esta serie de valores y características son capturados por *Wireshark* 
en formato hexadecimal para expresar la cadena de bits que constituye 
la trama.

![GET request](GET-request.jpg "Esquema de una petición GET con su respuesta")
>>>>>>>>>>>>>>>Esquema de una comunicación cliente-servidor.


**El campo *frame type*** indica el tipo de frame del paquete que se ha 
capturado o emitido en la comunicación. 

Los valores que este campo puede adoptar son:
- Data Frame.
- Management Frame.
- Control Frame.

En función de la acción que esté resolviendo el protocolo adoptará un tipo u otro.

Sin embargo hay **campos que no podemos capturar** como el **CRC (cyclic redundancy check)**
que está presente en la trama para realizar las comprobaciones pertinentes en cuanto a la 
detección de errores en la comunicación. Este campo no es visible porque permanece en la 
tarjeta de red en lugar de ser transferido a la aplicación de *Wireshark*.

La popularidad del campo **CRC** recae en su sipleza y gran efectividad en cuanto a detección
y correción de errores. 

> El emisor y el receptor deben estar de acuerdo en un
> patrón de r+1 bits, que se conoce como generador (G).
> El bit más significativo de G debe ser “1”.
>
> Para una determinada secuencia de datos D, el emisor
> añadirá r bits adicionales R, de modo que los r+d bits
> resultantes sean exactamente divisibles por G.*

**En resumen los aspectos generales son los siguientes:**

- Tecnología LAN más utilizada.
- Funciona en la capa de enlace de datos y en la capa física.
- Familia de tecnologías de redes que se define en los estándares IEEE 802.2 y 802.3.
<br>
<br>

***

### PROTOCOLO ARP (Address Resolution Protocol) 

    El protocolo ARP suele ser vinculado con la capa de red ya que este ocupa
    la labor de reolución de direcciones. Se encarga de localizar la dirección 
    del hardware relacionado con una dirección IP concreta.

> Esta dirección del hardware se conoce como *Ethernet MAC*.
> Dicha dirección está expresada por un identificador de 48b
> y que es único desde su fabricación.

El protocolo ARP toma la responsabilidad de coordinar las direcciones físicas
y lógicas en la comunicación mediante la red. Este protocolo se ayuda por la
creación de una tabla de direcciones que emplea para la búsqueda.

> Esta tabla se ubica en una memoria caché.
>> La tabla es recurrida por los equipos para comunicarse.
>> De no existir el vínculo es ARP quien arbitra la solicitud.
>> Todos los equipos dentro de la misma red comparan esta dirección
>> fallida con la suya propia y emiten la respuesta al coincidir. 
>> Finalmente el par de direcciones es almacenado.


Se puede **relacionar ARP** con cuatro casos que se dan en la comunicación de dos hosts
- Hay dos *hosts* en una **misma red** y se quieren comunicar
- Dos *hosts* quieren comunicarse a través de un *router* **desde redes diferentes**.
- Cuando un *router* emite un paquete a **través de un router** a un *host*.
- **Dentro de la misma red**, un *router* quiere emitir un paquete a un *host*.

Se **puede caracterizar un paquete ARP** por una serie de campos que emplea para 
atender sus solicitudes de enlace:
- Tipo de hardware (*Hardware address space*)
- Tipo de protocolo (*Protocol address space*) 
- Logitud de ID hardware  (*Hardware address length*)
- Logitud de ID protocolo (*Protocol address length*)
- Operación (*Operation code*) 
- direcciones del hardware (*Source/target hardware address*) 
- direcciones del protocolo (*Source/target protocol address*)
> Las longitudes se dan en bytes.

>Los campos de direcciones de hardware y protocolo se expanden en otros dos.


Especifica el tipo de hardware; ejemplos son Ethernet o Packet Radio Net.

Especifica el tipo de protocolo, el mismo que en el campo de tipo EtherType en la cabecera de IEEE 802.

Especifica la longitud(en bytes) de la dirección hardware del - paquete. Para IEEE 802.3 e IEEE 802.5 será de 6.

Especifica la longitud(en bytes) de las direcciones del protocolo en el paquete. Para IP será de 4.

Especifica si se trata de una petición(1) o una solicitud(2) ARP.

Contiene las direcciones física hardware. En IEEE 802.3 son direcciones de 48 bits.

Contiene las direcciones del protocolo. En TCP/IP son direcciones IP de 32 bits.