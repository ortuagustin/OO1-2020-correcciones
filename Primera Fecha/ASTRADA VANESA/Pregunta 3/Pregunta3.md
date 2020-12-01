# Enunciado

Dado el siguiente diagrama de clases

![UML](Pregunta1.png)

implemente el siguiente método (y lo que se considere necesario) :

`Curso>>mejorPromedio`

que retorna el alumno con el mejor promedio de calificaciones.

Asuma que lo que se indica en el diagrama de UML ya está programado.

# Solución

```smalltalk
Curso>>mejorPromedio
Alumno>>calcularPromedio
  ^(calificaciones sumNumbers: [:c | c nota ] / calificaciones size

Curso>>mejorPromedio

```

# Corrección

Incompleto

Corrigió: Agustín Ortu