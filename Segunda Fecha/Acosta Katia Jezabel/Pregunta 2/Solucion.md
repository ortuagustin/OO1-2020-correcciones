Object subclass: #Comercio

v.i.: productos

 Comercio >>initialize

      productos:= OrderedCollection new.

 Comercio >> obtenerProductos

      ^ self productos collect: [ :a1 :a2 | a1 stock < a2 stock].

 Comercio >> proveedoresDeProductosConStockMenorA: unStock

      ^ proveedores asSet: [:a | a obtenerProductos]