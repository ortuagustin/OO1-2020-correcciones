La solución es correcta. Algunos comentarios:

1. Dado que el título y el cuerpo del Email, según se indica en el UML, son String, se debería haber usado el mensaje #size para obtener el largo
2. En Email>>devolverTamanio, se puede llevar a un método la expresión que suma los adjuntos:

Email >> tamanoAdjuntos
  ^ adjuntos sumNumbers: [ :adjunto | adjunto tamano ]

Email >> devolverTamanio
  ^ self titulo sizeInMemory + self cuerpo sizeInMemory + self tamanoAdjuntos

3. El nombre del mensaje Carpeta>>verificarTamanio es un poco contraintuitivo, no está verificando algo del tamaño, se podría llamar simplemente "tamaño". Idem Email>>devolverTamanio

Corrigió Agustín Ortu