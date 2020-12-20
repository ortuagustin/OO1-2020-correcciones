Object subclass: Comercio

v.i: productos



Comercio >> initialize

productos:= OrderedCollection new.



Comercio >> proveedoresDeProductosConStockMenor: unStock

|  var |



var := productos select: [ :prod | prod stock < unStock ].

var collect: [ :each | each proveedor ].

^var asSet