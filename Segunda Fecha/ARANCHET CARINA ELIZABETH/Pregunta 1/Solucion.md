Distribuidora>>usuarioConMayorConsumoDurante:unDateLapse

   ^usuarios detectMax:[:usuario|usuario consumoMaximo:unDateLapse]

Usuario>>consumoMaximo:unDateLapse

|total|

total:=consumos select:[:aux|aux unDateLapse includesDate:fecha]

^total sumNumbers:[:aux|aux consumoEnergiaActiva]



Consumo>>fecha

^fecha

Consumo>>consumoEnergiaActiva

     ^consumoEnergiaActiva