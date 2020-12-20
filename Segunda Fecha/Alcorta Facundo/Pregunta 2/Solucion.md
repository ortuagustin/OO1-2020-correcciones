Object subclass #ClienteDeCorreo
v.i.: inbox, capertas
ClienteDeCorreo>>carpetasPesadas
^carpetas select :[ :carpeta | carpeta tamañoCarpeta > 1 ]

Object subclass #Carpeta
v.i.: emails
Carpeta>>tamañoCarpeta
^ emails detectMin : [ :email | email tamañoEmail ]

Object subclass #Email
v.i.: adjuntos
Email>>tamañoEmail
| tamTitulo tamCuerpo tamArchivo |
tamCuerpo := cuerpo sizeInMemory.
tamTitulo := titulo sizeInMemory.
tamArchivo := adjuntos sumNumbers: [ :adjunto | adjunto tamaño ].
^ (tamañoTitulo + tamañoCuerpo + tamañoArchivo)