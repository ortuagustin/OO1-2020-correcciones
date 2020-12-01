# Enunciado

Dado el siguiente diagrama de clases

![UML](Pregunta1.png)

implemente el siguiente método (y lo que se considere necesario) :

Curso>>alumnosOrdenAlfabetico

que debe retornar una colección con los alumnos inscriptos en el curso, ordenados alfabéticamente por nombre completo.

Asuma que lo que aparece en el diagrama de UML ya está implementado.

# Solución

```smalltalk
Curso>>alumnos
    ^alumnos.

Curso>>alumnoOrdenAlfabetico
    ^alumnos sort: [:alum1 :alum2 | alum1 nombreCompleto < alum2 nombreCompleto].
```

# Corrección

La solución es incorrecta, los errores son los siguientes:

1. No es necesario definir el mensaje #alumnos en Curso
2. El uso del mensaje #sort tiene varios problemas:
   a. Está definido en la clase SequenceableCollection, que es subclase de Collection; por lo tanto, estamos asumiendo que el Curso tiene un determinado tipo de colección; lo ideal es no asumir nada y utilizar la superclase más abstracta posible, en este caso, Collection. Si el curso utilizara colecciones de otra jerarquia (por ej. Set), este código no funciona, porque no se puede ordenar un Set.
   b. Es un mensaje que muta la colección, es decir, reordena la colección interna del Curso, cuando la intención del mensaje es devolver una colección ordenada de los alumnos utilizando un criterio particular; es decir, es un mensaje que tiene un side-effect (efecto secundario)

Lo adecuado es utilizar el mensaje Collection>#asSortedCollection: sortBlock, así:

Curso>>alumnoOrdenAlfabetico
    ^alumnos asSortedCollection: [:alum1 :alum2 | alum1 nombreCompleto < alum2 nombreCompleto].

El cual no tiene ninguno de los problemas enunciados anteriormente: #asSortedCollection crea una nueva colección con los elementos que ya contiene la colección, y luego aplica el criterio de orden especificado en el parametro sortBlock

Corrigió: Agustín Ortu