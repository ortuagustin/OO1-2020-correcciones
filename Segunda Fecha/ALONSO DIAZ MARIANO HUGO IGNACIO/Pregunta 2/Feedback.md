La solución es correcta. Algunos comentarios:

1. Dado que el título y el cuerpo del Email, según se indica en el UML, son String, se debería haber usado el mensaje #size para obtener el largo
2. En Email>>calcularTamanio, se puede llevar a un método la expresión que suma los adjuntos:

Email >> tamanoAdjuntos
  ^ adjuntos sumNumbers: [ :adjunto | adjunto tamano ]

Email >> calcularTamanio
  ^ self titulo sizeInMemory + self cuerpo sizeInMemory + self tamanoAdjuntos

3. El nombre del mensaje Carpeta>>calcularTamanioEmails da la idea de que le estoy pidiendo a la carpeta que calcule el tamaño de los emails, cuando en realidad está devolviendo una colección filtrada de los email que tiene. Podria llamarse #emailsPesados por ejemplo, siguiendo la idea del mensaje #carpetasPesadas

Corrigió Agustín Ortu