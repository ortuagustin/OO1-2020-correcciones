# Enunciado

Dado el siguiente diagrama de clases

![UML](Pregunta1.png)

implemente el siguiente método (y lo que se considere necesario) :

Curso>>alumnosOrdenAlfabetico

que debe retornar una colección con los alumnos inscriptos en el curso, ordenados alfabéticamente por nombre completo.

Asuma que lo que aparece en el diagrama de UML ya está implementado.

# Solución

```smalltalk
Curso >> alumnosOrdenAlfabetico
  ^ alumnos asSortedCollection: [:a1 :a2 | a1 nombreCompleto < a2 nombreCompleto]
```

# Corrección

La solución es correcta. Como sugerencia, se podrían usar nombres más descriptivos para las variables temporales del bloque

Corrigió: Agustín Ortu