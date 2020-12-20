ClienteDeCorreo>>carpetasPesadas

^carpetas select:[:carp | carp tamano > 1].





Carpeta>>tamano

^emails sumNumbers:[:e | e tamanoE].





Email>>tamanoE

| tamanoTit tamanoCuerpo tamanoArch|

tamanoArch:=adjuntos sumNumbers:[:arch |arch tamano].

tamanoCuerpo:= cuerpo sizeInMemory.

tamanoTitulo:= titulo sizeInMemory.

^(tamanoTit+tamanoCuerpo+tamanoArch)