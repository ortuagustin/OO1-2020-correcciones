La solución no es correcta:

1. Se debería delegar en Usuario la responsabilidad de determinar si tuvo un consumo en los últimos 3 (o N) días
2. La expresión (Date today-(unUsuario ultimoConsumo) asDays > 3) no es correcta, ya que está restando un objeto Date con un objeto Consumo

Corrigió Agustín Ortu