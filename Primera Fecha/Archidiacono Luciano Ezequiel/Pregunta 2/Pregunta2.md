# Enunciado

 Dado el siguiente diagrama, implemente la clase ListaDeTareas incluyendo lo necesario para su instanciación e inicialización, y los métodos

#pendientes  que retorna la colección de tareas que estén incompletas.

#siguientePorPrioridad que retorna la tarea incompleta de mayor prioridad (si hay mas de una con la prioridad más alta retorna cualquiera de ellas, si no hay tareas retorna nil).

Asuma que la clase Tarea ya está implementada.
![UML](Pregunta2.png)

# Solución

```smalltalk
Object subclass ListaDeTareas
v.i.: items

>> initialize

   items := OrderedCollection new.

>> agregarTarea: unaTarea

   items add: unaTarea

>> pendientes

  ^ items select: [ :each | (each completa) not]

>> siguientePorPrioridad

  ^ self pendientes isEmpty
       ifTrue: [ nil ]
       ifFalse: [ (self pendientes sort: [ :tarea1 :tarea2 | tarea1 prioridad <= tarea2 prioridad ]) first ]
```

# Corrección

La solución está aprobada, sin embargo, algunos comentarios:

1. El método #pendientes, se podría haber implementado usando #reject en lugar de #select, quedaría asi:

ListaDeTareas>>pendientes
  ^ items reject: [ :each | each completa]

2. En el mensaje #siguientePorPrioridad, se utiliza #sort, que está definido en la clase SequenceableCollection, que es subclase de Collection; esto nos restringe a una subrama de la jerarquia de Collection. Por ejemplo, no podríamos usar un Set. Lo ideal es siempre utilizar mensajes de la superclase más abstracta posible, en este caso Collection. Esto nos permite tener mayor flexibilidad a la hora de que clase concreta queremos instanciar. Sería justificable en este dominio instanciar una SortedCollection en lugar de una OrderedCollection, ya que de esta manera, la colección se encargaría siempre de mantener la propiedad de orden.


Corrigió: Agustín Ortu