Email >> devolverTamanio

 ^ titulo sizeInMemory + cuerpo sizeInMemory + adjuntos sumNumbers: [ :a | a tamano]



Carpeta >> verificarTamanio

^ emails sumNumbers: [ :email | email devolverTamanio]



ClienteDeCorreo >>  carpetasPesadas

  ^carpetas select [ :carpeta | carpeta verificarTamanio > 1]