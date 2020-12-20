Consumo >> fecha

 ^fecha



Usuario >> ultimoConsumoFecha

 ^consumos detectMax: [ :consumo | consumo fecha]



Distribuidora>>eliminarUsuario: unUsuario

  usuario contains: unUsuario

 ifTrue:[(unUsuario ultimoConsumoFecha - Date today) days > 3. ifTrue[ usuarios remove: unUsuario ]]
