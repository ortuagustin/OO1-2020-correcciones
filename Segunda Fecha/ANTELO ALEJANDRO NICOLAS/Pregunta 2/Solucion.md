Object subclass Recetario

v.i.: recetas



Recetario>>recetasLigth

^recetas select: [ :receta | receta caloriasReceta < 500]



Object subclass Receta

v.i.: ingredientes



Receta>>caloriasReceta

^ingredientes sumNumbers: [:ingrediente | ingrediente cantCalorias]



Object subclass Ingredientes

v.i.: cantidadEnGramos, alimento



Ingredientes>>cantCalorias

^ alimento caloriasPorGramo * cantidadEnGramos.