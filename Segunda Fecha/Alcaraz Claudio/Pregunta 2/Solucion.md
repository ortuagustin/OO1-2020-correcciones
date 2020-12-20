Objetc subclass: #Recetario

   v.i: receta

    >>initialize

     recetas:= OrderedCollection new

   >>recetasLight()

       ^recetas select:[Receta: | Receta calorias <500 ]

Objetc subclass: #Receta

      v.i: ingrediente

      >>initialize

     >>calorias

     ^ingredientes sumNumbrers: [:ingrediente | ingrediente caloriasTot]

Objetc subclass: #ingrediente

     v.i: alimento

      >>initialize

     >>caloriasTot

     ^cantidadEnGramos*alimento caloriasPorGramos