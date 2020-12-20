Object subclass: #ClienteDeCorreo

v.i: carpetas

ClienteDeCorreo>> carpetasPesadas

     ^carpetas select: [:each | each carpetaTamano>1]

Object subclass: #Carpeta

v.i: emails

Carpeta >> carpetaTamano

 ^ email sumNumbers: [:eachl | each tamanoTotal]

Object subclass: #Email

v.i: adjuntos

Email>> tamanoTotal

  ^(self titulo sizeInMemory + self cuerpo sizeInMemory + self tamanoArchivos)

Email>> tamanoArchivos

     ^ self adjuntos sumNumbers: [:each | each tamano]