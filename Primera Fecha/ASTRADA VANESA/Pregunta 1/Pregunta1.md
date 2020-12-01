# Enunciado

 Dado el siguiente diagrama, implemente la clase ListaDeTareas incluyendo lo necesario para su instanciación e inicialización, y los métodos

#pendientes  que retorna la colección de tareas que estén incompletas.

#siguientePorPrioridad que retorna la tarea incompleta de mayor prioridad (si hay mas de una con la prioridad más alta retorna cualquiera de ellas, si no hay tareas retorna nil).

Asuma que la clase Tarea ya está implementada.
![UML](Pregunta2.png)

# Solución

```smalltalk
Object subclass: #ListaDeTareas

>> initialize
   items := OrderedCollection new

>> pendientes
   ^items reject: [:item | item completa]

>> siguientePorPrioridad
   self pendientes ifNotNil: [^(self pendientes sort: [:item | item prioridad]) first] .
   ^nil
```

# Corrección

La solución está aprobada, sin embargo, algunos comentarios para #siguientePorPrioridad:

1. La forma de verificar si una colección está vacía es usando el mensaje #isEmpty, no #ifNotNil; la expresión "self pendientes" nunca va a evaluar a nil, porque si al evaluar el #reject, ningún elemento cumple la condición, o bien, la colección items está vacía, el resultado, es una colección vacía
2. Se utiliza #sort, que está definido en la clase SequenceableCollection, que es subclase de Collection; esto nos restringe a una subrama de la jerarquia de Collection. Por ejemplo, no podríamos usar un Set. Lo ideal es siempre utilizar mensajes de la superclase más abstracta posible, en este caso Collection. Esto nos permite tener mayor flexibilidad a la hora de que clase concreta queremos instanciar. Sería justificable en este dominio instanciar una SortedCollection en lugar de una OrderedCollection, ya que de esta manera, la colección se encargaría siempre de mantener la propiedad de orden.


Corrigió: Agustín Ortu