Object subclass #Comercio

v.i:productos

Comercio>>proveedoresDeProductoConStockMenor stock

 |proveedores|

proveedores := productos collect : [ :producto | producto stockMenor: stock].

^ (proveedores)asSet.





Object subclass #Prodcuto

 v.i: proveedor

Producto>> stockmenor unStock

 (unStock > self stock)

 ifTrue : [ ^self proveedor]