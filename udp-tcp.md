----- DOCUMENTO DE RESPUESTAS PARA LA P3 -----

RESUMEN:

   Objetivos -> comprender estructuras y funciones UDP y TCP | Análisis del inicio y cierre de TCP y funcionamiento ACK en TCP.

    · CABECERA UDP -> P ORIGEN (primeros 2B ) | P DESTINO (3er y 4to Byte) | 
                      Checksum (5to y 6to B)  |  Longitud (7mo y 8vo Byte)

    · PROTOCOLO TCP -> orientado a conexión, confiable y control de flujo
    
    · CABECERA TCP -> PUERTO ORIGEN (0 - 15B) | PUERTO DESTINO (16 - 32B)
                            Número de secuencia (32 - 63 B)
                      OFF (4b) | RES 6B + 6B  | VENTANA (11vo y 12vo B)
                      PUNTERO (13vo y 14vo B) | Checksum (15vo y 16 B)
                        OPC (últimos 4 bytes - 0 si no hay 32 si hay)

    · RESUMEM INICIO Y CIERRE

    . RESUMEN ACK EN TCP


PREGUNTAS DE ELEMENTOS BÁSICOS DE LA CABECERA UDP


    1 - El campo de longitud, ¿qué longitud indica la longitud de la cabecera, de 
    la carga útil o del segmento completo? Verifique su hipótesis con el paquete UDP capturado.

    Indica el tamaño del datagrama, por ende la longitud del segmento completo. Esto 
    se deduce además porque el tamaño indicado en el campo de longitud es de 52 bytes 
    y , comprobando en la sección de payload, que es la carga útil, el número en 
    bytes es menor.

    Cabe destacar que la longitud mínima será 8, que es el tamaño de la cabecera.


    2 - ¿Cuál es el número máximo de bytes que puede contener la carga útil o payload 
        en UDP? 
    
    Dado que el campo de longitud es de 16 bits, puede haber en teoría un valor
    desde 0 hasta 65.535 Bytes a los cuales se les restan siempre los 8 bits de la  
    cabecera. Sin embargo el protocolo IPv4 impone una longitud máxima de 65,507    
    Bytes, lo cual viene dado de restar los 8 bytes de la cabecera UDP y los    
    consiguientes 20 bytes de la cabecera IP. 


    3 - ¿Cuál es el mayor número de puerto de origen que puede contener un paquete 
        UDP?

    Debido a que el campo de puerto de origen consta de 16 bits se puede seleccionar 
    un rango de 0 a 6535 puertos. Como es opcional, si no se usa es el 0, por lo que 
    deberíamos restarle uno al número de puertos direccionables si el origen espera una respuesta.

    
    4 - ¿Cuál es el número de protocolo UDP? De su respuesta en notación hexadecimal 
        y en decimal (mirar en la cabecera IP)

    El número de protocolo UDP es 17 o 0x11 en hexadecimal.


    5 - Busque información sobre "UDP" y determine las partes del datagrama sobre las 
        que se lleva a cabo la suma de comprobación (checksum).

    Esta parte, la cual además es opcional, se localiza en los ultimos dos bytes de la cabecera del protocolo UDP. Entre los bits 47 y 63.

    
    6 - Examine una pareja de paquetes UDP en los cuales el primer paquete haya sido 
        enviado por su ordenador y el segundo paquete sea una respuesta al primer 
        paquete. Describa la relación entre los números de puerto en ambos paquetes.
    
        En ambos paquetes, al existir una comunicación, ambas cabeceras UDP tienen puertos tanto de origen como de destino. 

        Lo que sucede con los puertos de la pareja de paquetes que se comunican es que se han intercambiado. La relación es inversa.


PREGUNTAS DE CAPTURA DE TRÁFICO TCP

PREGUNTAS DE INICIO Y CIERRE DE CONEXIÓN EN TCP

PREGUNTAS DE ACK EN TCP