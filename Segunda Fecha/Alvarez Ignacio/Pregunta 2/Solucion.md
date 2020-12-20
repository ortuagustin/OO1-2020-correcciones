Comercio>>proveedoresDeProductosConStockMenorA: unStock

| stockMenor |

stockMenor := Set new.

productos do: [ :each | each stock < unStock ifTrue:[ stockMenor add: each proveedor ] ].

^stockMenor