# Enunciado

Dado el siguiente diagrama de clases

![UML](Pregunta2.png)

Implementar el siguiente método (y lo que se considere necesario) :

Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos

que retorna true si todos los elementos de unaColeccionDeAlumnos están entre los alumnos inscriptos al curso.

Asuma que lo que aparece en el diagrama de UML ya está implementado.

# Solución

```smalltalk
Alumno>>estoyEnLaColeccionDeAlumnosInscriptos:alumnosInscriptosAlCurso
    ^alumnosInscriptosAlCurso includes:self.

Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos
    ^(unaColeccionDeAlumnos select: [:each | each estoyEnLaColeccionDeAlumnosInscriptos:alumnos])size =  unaColeccionDeAlumnos size
```

# Corrección

La solución es incorrecta, ya que no utiliza los mensajes apropiados de colecciones; además, la asignación de responsabilidades no es adecuada, el responsable de saber si un Alumno está inscripto en un Curso, es el propio Curso, dado que él administra sus colecciones; no tiene sentido que el Curso le delege al Alumno para ver si el mismo está incluido en una colección.

Algunas variantes que resuelven este ejercicio, son:

Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos
    ^ alumnos includesAll: unaColeccionDeAlumnos

Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos
    ^ unaColeccionDeAlumnos allSatisfy: [ :each | alumnos includes: each ]

Corrigió: Agustín Ortu