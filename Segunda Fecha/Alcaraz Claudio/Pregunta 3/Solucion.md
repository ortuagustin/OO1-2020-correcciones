Object subclass: #ClienteDeCorreo
v.i.: carpetas

ClienteDeCorreo>> initialize
carpetas := OrderedCollection new.

ClienteDeCorreo>>carpetasPesadas

^carpetas select:[archivo|archivo tamano>1]

Object subclass: #Carpeta
v.i.: emails

Carpeta>> initialize
carpetas := OrderedCollection new.

Carpeta>>tamañoCarpeta

^ emails sumNumbers: [ :email | email tamañoEmail ]

Object subclass: #Email
v.i.: adjuntos

Email>> initialize
adjuntos := OrderedCollection new.

Email>>tamañoEmail

| tamañoTitulo tamañoCuerpo tamañoArchivo |
tamañoTitulo := titulo sizeInMemory.
tamañoCuerpo := cuerpo sizeInMemory.
tamañoArchivo := adjuntos sumNumbers: [ :adjunto | adjunto tamaño ].
^ tamañoTitulo + tamañoCuerpo + tamañoArchivo
