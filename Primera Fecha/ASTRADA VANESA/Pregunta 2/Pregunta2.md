# Enunciado

Dado el siguiente diagrama de clases


![UML](Pregunta1.png)

Implementar el siguiente método (y lo que se considere necesario) :

Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos

que retorna true si todos los elementos de unaColeccionDeAlumnos están entre los alumnos inscriptos al curso.

Asuma que lo que aparece en el diagrama de UML ya está implementado.

# Solución

```smalltalk
Alumno>>noEsAlumno: unAlumno
   ^(self nombreCompleto != unAlumno nombreCompleto)


Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos
|ins|
ins := true
unaColeccionDeAlumnos do: [:alum |  (alumnos includes: [:a | a noEsAlumno: alum ]) ifTrue: [ins:=false])]
^ins

```

# Corrección

La solución no es correcta, se debe utilizar el protocolo adecuado de colecciones; #do nos lleva a una solución procedural y a reinventar la rueda, ya que hay mensajes de mayor nivel de abstracción que resuelven este problema.

Algunas variantes que resuelven este ejercicio, son:

Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos
    ^ alumnos includesAll: unaColeccionDeAlumnos

Curso>>seEncuentranInscriptos: unaColeccionDeAlumnos
    ^ unaColeccionDeAlumnos allSatisfy: [ :each | alumnos includes: each ]

Corrigió: Agustín Ortu