# Enunciado

Dado el siguiente diagrama de clases


![UML](Pregunta3.png)

Implementar el siguiente método (y lo que se considere necesario) :

Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos

que retorna true si todos los elementos de unaColeccionDeAlumnos están entre los alumnos inscriptos al curso.

Asuma que lo que aparece en el diagrama de UML ya está implementado.

# Solución

```smalltalk
Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos
| colTemp |
colTemp := unaColeccionDeAlumnos collect: [ :e | alumnos includes: e].
^(colTemp includes: false) not.

"Creo que estoy 'reinventando la rueda', pero no se me ocurre qué método usar para comparar las dos colecciones ya que no se de qué tipo son"
```

# Corrección

La solución no es correcta, debido a que no utiliza los mensajes apropiados de colecciones. Algunas variantes que resuelven este ejercicio, son:

Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos
    ^ alumnos includesAll: unaColeccionDeAlumnos

Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos
    ^ unaColeccionDeAlumnos allSatisfy: [ :each | alumnos includes: each ]

Corrigió: Agustín Ortu