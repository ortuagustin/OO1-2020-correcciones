Object subclass : #Recetario
v.i.: recetas
Recetario>>recetasLight()
    recetas isEmpty ifTrue:[^ 0].
   ^ recetas set : [ :receta |
]




receta>>cantidadCalorias
^
