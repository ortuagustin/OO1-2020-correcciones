# Enunciado

![UML](Pregunta3.png)

Escriba los métodos necesarios para poder crear e inicializar una instancia de la clase Factura de forma adecuada. Una vez creada la instancia de Factura, no pueden agregarse items ni cambiarse la fecha, siendo esta la del dia en la que se crea dicha instancia.

# Solución

```smalltalk
(Metodo de instancia)

Factura>> initialize
fecha:=Date today.
items:=OrderedCollection new.
___________________________________________________________________
(Metodo de instancia)

Factura>>nuevaFacturaConItems: unaColeccionDeItems
items addAll: unaColeccionDeItems
___________________________________________________________________
(Metodo de clase)

Class>> Factura>>nuevaFacturaConItems: unaColeccionDeItems
^(self new) nuevaFacturaConItems: unaColeccionDeItems
___________________________________________________________________
```

# Corrección

La solución es correcta

Corrigió: Agustín Ortu