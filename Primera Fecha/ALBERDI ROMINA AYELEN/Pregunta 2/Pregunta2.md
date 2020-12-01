# Enunciado

Dado el siguiente diagrama de clases

![UML](Pregunta2.png)

Implementar el siguiente método (y lo que se considere necesario) :

Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos

que retorna true si todos los elementos de unaColeccionDeAlumnos están entre los alumnos inscriptos al curso.

Asuma que lo que aparece en el diagrama de UML ya está implementado.

# Solución

```smalltalk
Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos
    ^unaColeccionDeAlumnos allSatisfy: [:each| alumnos includes: each]
```

# Corrección

La solución es correcta; como comentario menor, existe el mensaje #includesAll que lo resuelve de manera más directa :)

Corrigió: Agustín Ortu