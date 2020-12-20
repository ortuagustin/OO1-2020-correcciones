Distribuidora>>initialize

usuarios:= OrderedCollection new.



Distribuidora>>eliminarUsuario:unUsuario

| usuario dias  |

usuario := usuarios detect:[:each | each = unUsuario].

dias := (usuario ultimoConsumo - Date today) asDays.

(dias>3) ifTrue:[ usuarios remove:unUsuario] .



Usuario>>ultimoConsumo

consumos detectMax:[:consumo | consumo fecha]



Consumo>>fecha

^fecha.