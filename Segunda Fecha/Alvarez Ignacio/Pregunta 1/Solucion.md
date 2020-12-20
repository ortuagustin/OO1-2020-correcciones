Object subclass #Carpeta

v.i: email

>> tamañoEmail

    "devuelve una colleccion solo de los email que cumplan la condicion"

    ^email select:[ :email | email > 100000]





Object subclass #ClienteDeCorreo

v.i: carpetas

>> carpetasPesadas

      "devuelve una coleccion de las carpetas con los email que sean menores a 1mb, recorriendo cada carpeta"

     ^carpeta collect: [ :carpeta | carpeta tamañoEmail ]

Comentarios
