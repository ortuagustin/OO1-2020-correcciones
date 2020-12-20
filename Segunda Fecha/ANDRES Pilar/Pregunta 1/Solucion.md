Object subclass: #Distribuidora

v.i: precio KWh usuarios

Distribuidora >> usuarioConMayorConsumoDurante: unDateLapse

   ^usuarios detectMax: [:each | each consumosMax: unDateLapse]



Object subclass: #Usuarios

v.i: nombre domicilio

Usuarios>> consumosUsuario: unDateLapse

 ^consumos select:[:each | each unDateLapse includesDate: fecha]



Usuarios>> consumosMax: unDateLapse

  ^consumosUsuario:unDateLape sumNumbers:[:each | each consumoEnegiaActiva]





Object subclass: #Consumo

v.i: consumoEnergiaActiva fecha consumoEnergiaReactiva

Consumo>> consumoEnergiaActiva

 ^consumoEnergiaActiva



Consumo>>fecha

  ^fecha