Object subclass: # Consumo
>> difDias
^ Date today subtractDays: fecha

>>fecha

^fecha

Object subclass: # Usuario
>> diferenciaUltConsumo
^ consumos last difDias

Object subclass: # Distribuidora

v.i :usuario
 eliminarUsuario: unUsuario

(usuarios includes: unUsuario)

ifTrue: [ unUsuario diferenciaUltConsumo > 3)

ifTrue: [usuarios remove: unUsuario] ]