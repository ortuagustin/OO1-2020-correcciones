Object subclass: #Recetario

v.i: recetas

>>recetasLight

^ recetas flatCollect: [ :receta | receta ingredientes:receta ]




Object subclass: #Receta

v.i: ingredientes



>>ingredientes: receta

"retorna la colleccion con elementos que solo pesan menos de 500 calorias calculando por cada elemento de la colleccion"

^ ingredientes select: [ :unIngrediente | unIngrediente getcantGramos * unIngrediente caloriasIngrediente: unIngrediente <= 500 ]




Object subclass: #Ingredientes

v.i: alimento

"se inmplementan getters para calcular en otro momento la cantidad de calorias por ingrediente"



>>getcantGramos

^cantidadEnGramos

>>caloriasIngrediente: unIngrediente

^alimento caloriasPorGramo