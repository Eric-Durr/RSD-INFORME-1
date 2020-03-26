## Protocolo Ethernet y ARP
    En este apartado se hablará sobre los protocolos Ethernet
    y ARP. Se entrará en detalles sobre sus cabeceras y funcionamiento. 
    
    Tanto Ethernet como ARP se sencuentran en
    la capa de enlace. 



### PROTOCOLO ETHERNET

**Antecedentes:**
> El protocolo Ethernet tiene como precursor al protocolo ALOHA
> siendo este una mejora basada en muchos de los conceptos del
> protocolo anterior.

> Este protocolo es el más usado para areas locales, cableadas,
> a nivel de enlace.

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

> El estudio de este protocolo durante la práctica no ha 
> profundizado en cuestiones demasiado concretas. Los aspectos
> que se presentan son en su mayoría básicos. 


![Eth TRAMA](Trama.png "Imagen de la trama ethernet")
>>>>>>>>>>>>>>>Imagen que expresa la trama ethernet.


Dependiendo del estandar de Ethernet empleado el marco puede variar.
Algunos elementos más generales pueden ser similares entre varios de 
estos. Por ejemplo en *Wireshark* se muestran los iguientes:


- Destino
- Origen
- tipo



### PROTOCOLO ARP (Address Resolution Protocol)