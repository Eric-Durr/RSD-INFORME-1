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


PREGUNTAS DE CAPTURA DE TRÁFICO TCP

PREGUNTAS DE INICIO Y CIERRE DE CONEXIÓN EN TCP

PREGUNTAS DE ACK EN TCP