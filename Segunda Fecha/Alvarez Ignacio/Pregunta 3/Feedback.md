La solución no es correcta:

1. No tiene mucho sentido que el método Receta>>ingredientes tenga como argumento la receta. ¿Quién sería self en ese contexto? Además, dicho argumento no se usó en la implementación.
3. Sobre Recetario>>recetasLight:
   - El retorno del método no es adecuado, ya que debería ser una colección de objetos Receta
   - ¿Por qué usar #flatCollect? El método debería devolver una colección filtrada de las recetas que ya conoce, lo correcto es usar #select
4. Hay envidia de atributos para calcular las calorías

Una solución más adecuada, podría ser:

Recetario>>recetasLight
  ^ recetas select: [receta: | receta calorias < 500]

Receta>>calorias
  ^ ingredientes sumNumbrers: [:ingrediente | ingrediente caloriasTotales]

Ingrediente>>caloriasTotales
  ^ alimento caloriasPara: cantidadEnGramos.

Alimento>>caloriasPara: unaCantidadEnGramos
  ^ caloriasPorGramo * unaCantidadEnGramos

Corrigió Agustín Ortu