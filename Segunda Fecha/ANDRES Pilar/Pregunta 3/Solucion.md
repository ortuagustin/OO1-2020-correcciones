Object subclass: #Distribuidora

v.i: precioKWh usuarios



Distribuidora >> eliminarUsuario: unUsuario

 |today|

 today:= Date today.

 (usuarios includes: unUsuario) ifTrue: [((today - unUsuario ultimoConsumo) asDays > 3)

ifTrue:[usuarios remove: unUsuario]]





Object subclass: #Usuario

v.i: nombre domicilio



Usuario >>ultimoConsumo

 ^consumos detectMax: [:consumo | consumo fecha]



Object subclass: #Consumo

v.i: fecha consumoEnergiaActiva consumoEnergiaReactiva

Consumo >> fecha

 ^fecha