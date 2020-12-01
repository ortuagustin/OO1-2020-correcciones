# Enunciado

![UML](Pregunta3.png)

Escriba los métodos necesarios para poder crear e inicializar una instancia de la clase Factura de forma adecuada. Una vez creada la instancia de Factura, no pueden agregarse items ni cambiarse la fecha, siendo esta la del dia en la que se crea dicha instancia.

# Solución

```smalltalk
Factura class >> newFacturaConItems: unosItems
| factura |
factura := self new.
factura inicializadorFacturaConItems: unosItems.
^factura

Factura >> inicializadorFacturaConItems: unosItems
fecha := Date today.
items := unosItems
```

# Corrección

La solución es correcta

Corrigió: Agustín Ortu