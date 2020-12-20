La solución no es correcta:

1. Esta expresión, en Carpeta>>tamañoEmail es incorrecta

email select:[ :email | email > 100000]

Ya que en el objeto email no se definió el mensaje #>

2. Falta un método en el Email que realice el calculo del tamaño (es decir, la suma de largo del título, el largo del cuerpo, y del tamaño de sus adjuntos)

Corrigió Agustín Ortu