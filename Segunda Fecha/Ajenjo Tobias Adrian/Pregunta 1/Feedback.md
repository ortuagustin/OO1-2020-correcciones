La solución no es correcta:

1. Se debería delegar en Usuario la responsabilidad de determinar si tuvo un consumo en los últimos 3 (o N) días
2. No es necesario "buscar" el Usuario con #detect, dado que ya lo recibimos por parámetro; de todos modos, si el usuario no existe en la colección, se lanzara una excepción en ejecución (por ello existe #detect:IfFound: y otras variantes). Es mas sencillo preguntar si el usuario existe en la colección con #includes, que retornara un Boolean
3. La expresión (usuario ultimoConsumo - Date today) no es correcta, ya que está restando un objeto Date con un objeto Consumo

Corrigió Agustín Ortu