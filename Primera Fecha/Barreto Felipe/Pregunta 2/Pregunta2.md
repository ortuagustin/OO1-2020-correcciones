# Enunciado

Dado el siguiente diagrama de clases

![UML](Pregunta2.png)

Implementar el siguiente método (y lo que se considere necesario) :

Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos

que retorna true si todos los elementos de unaColeccionDeAlumnos están entre los alumnos inscriptos al curso.

Asuma que lo que aparece en el diagrama de UML ya está implementado.

# Solución

```smalltalk
Curso >> seEncuentranInscriptos: unaColeccionDeAlumnos
^(alumnos includesAll: unaColeccionDeAlumnos)
```

# Corrección

La solución es correcta

Corrigió: Agustín Ortu