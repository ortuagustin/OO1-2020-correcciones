# Enunciado

Dado el siguiente diagrama de clases

![UML](Pregunta1.png)

implemente el siguiente método (y lo que se considere necesario) :

Curso>>alumnosOrdenAlfabetico

que debe retornar una colección con los alumnos inscriptos en el curso, ordenados alfabéticamente por nombre completo.

Asuma que lo que aparece en el diagrama de UML ya está implementado.

# Solución

```smalltalk
Object subclass: #Curso
v.i: alumnos

Curso>> initialize
    alumnos := OrderedCollection new

Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos
    ^ alumnos includesAll: unaColeccionDeAlumnos
```

# Corrección

La solución es correcta

Corrigió: Agustín Ortu