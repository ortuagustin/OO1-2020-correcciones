Object subclass: Recetario

v.i: recetas



Recetario  >> initialize

recetas := OrderedCollection new.



Recetario >> recetasLight

^recetas select: [ :receta | receta cantidadDeCalorias < 500 ]





Object subclass: Receta

v.i: calorias ingredientes

Receta  >> initialize

ingredientes := OrderedCollection new.



Receta  >> cantidadDeCalorias

^ ingredientes sumNumbers: [ :ingrediente | ingrediente calorias ]





Object subclass: Ingrediente

v.i.: alimento



Ingrediente >> calorias

^self cantidadEnGramos * (self alimento caloríasPorGramo)