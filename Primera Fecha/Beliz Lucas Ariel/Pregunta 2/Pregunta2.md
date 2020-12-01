# Enunciado

Dado el siguiente diagrama de clases

![UML](Pregunta2.png)

implemente el siguiente método (y lo que se considere necesario) :

`Curso>>mejorPromedio`

que retorna el alumno con el mejor promedio de calificaciones.

Asuma que lo que se indica en el diagrama de UML ya está programado.

# Solución

```smalltalk
Curso>>mejorPromedio
  |maxProm|
  maxProm:= 0.
  alumnos do: [ :each | each calculoPromedio > maxProm ifTrue: [ maxProm := each calculoPromedio ] ].
  ^ maxProm.

Alumno>>calculoPromedio

  ^ (clasificaciones sumNumbers: [ :each | each nota ] / clasificaciones size).
```

# Corrección

La solución no es correcta, debido a que utiliza #do, cuando se podrían usar mensajes de mayor nivel de abstracción. Por ejemplo #detectMax, o ordenar la colección y luego obtener el primer elemento

En el mensaje #calculoPromedio, si el alumno no tiene ninguna calificacion, se realiza una división por cero

El retorno del mensaje Curso>>mejorPromedio debe ser un objeto Alumno (aquel que tenga el mayor promedio), como lo especifica el enunciado

Corrigió: Agustín Ortu