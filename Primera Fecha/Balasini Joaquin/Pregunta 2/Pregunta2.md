# Enunciado

Dado el siguiente diagrama de clases


![UML](Pregunta1.png)

Implementar el siguiente método (y lo que se considere necesario) :

Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos

que retorna true si todos los elementos de unaColeccionDeAlumnos están entre los alumnos inscriptos al curso.

Asuma que lo que aparece en el diagrama de UML ya está implementado.

# Solución

```smalltalk
Object subclass: #Curso
v.i: coleccionDeAlumnosInscriptos

>>Inscribir: unAlumno

coleccionDeAlumnosInscriptos add: unAlumno

>>seEncuentranInscriptos: unaColeccionDeAlumnos

^coleccionDeAlumnosInscriptos includesAll: unaColeccionDeAlumnos
```

# Corrección

La solución es correcta

PD: No era necesario el método #inscribir :)

Corrigió: Agustín Ortu