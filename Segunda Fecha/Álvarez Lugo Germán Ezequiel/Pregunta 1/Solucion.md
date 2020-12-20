Object subclass; #Comercio

v,i: productos

Comercio >> initialize

 productos:= OrderedCollection new.



 Producto >> proveedor

 ^proveedor

 Producto >> stock

 ^stock



Comercio >> stockMenorA: unStock

   ^ productos select: [ :producto | producto stock < unStock ]



Comercio >> proveedoresDeProductosConStockMenorA: unStock

 |proveedores|

    proveedores:=(stockMenorA: unStock) collect: [:producto | producto proveedor]

   ^proveedores asSet