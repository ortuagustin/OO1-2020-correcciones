Object subclass:#Distribuidora

v.i.:precioKWH usarios



Distribuidora>>initialize

usuarios:=OrderedCollection new.



Distribuidora>>eliminarUsuario:unUsuario

   (usuarios includes:unUsuario)

ifTrue:[(Date today -(unUsuario ultimoConsumo)asDays > 3 )

ifTrue:[usuarios remove:unUsuario]]



Object subclass:#Consumo

v.i.: fecha consumoEnergiaReactiva consumoEnergiaActiva



Consumo>>initialize

fecha:=Date today.

Consumo>>fecha

    ^fecha

Object subclass:#Usuario

v.i.:nombre domicilio consumos

Usuarios>>initialize

consumos:=OrderedCollection new.

facturas:=OrderedCollection new.

Usuario>> ultimoConsumo

     ^consumos detectMax:[:consumo|consumo fecha]