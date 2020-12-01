# Enunciado

El diagrama de clases de UML que se muestra a continuación documenta parte del diseño simplificado de un cliente de correo electrónico.

![UML](Pregunta2.png)

Implemente el siguiente método de la clase ClienteDeCorreo:

#buscarDeAutor(autor:String)

que retorna todos los emails (considerando todas las carpetas) cuyo remitente (quien escribió ese email) es el igual al autor recibido por parámetro.



Asuma que todas las clases poseen sus constructores implementados, y que los métodos nombrados en las clases Carpeta e Email del diagrama de UML ya están implementados. Debe agregar los métodos que considere necesario en las diferentes clases para una buena implementación del método #buscarDeAutor(autor:String).

# Solución

```smalltalk
Carpeta >> buscarDeAutor: autor
^emails select:[:e | autor match: e remitente]

ClienteDeCorreo >> buscarDeAutor: autor
^carpetas collect:[:c | c buscarDeAutor: autor ]
```

# Corrección

La solución no es correcta, debido a que se está retornando una colección de colecciones. Se debe usar el mensaje #flatCollect, en lugar de #collect. Otra alternativa es realizar un #flattened luego del #collect.

Corrigió: Agustín Ortu