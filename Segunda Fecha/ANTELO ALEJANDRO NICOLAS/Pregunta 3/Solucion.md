Distribuidora >> usuarioConMayorConsumoDurante: unDateLapse

^ usuarios detectMax: [ :usuario| usuario consumido: unDateLapse ]



Usuario >> consumido: unDateLapse

^consumos sumNumbers: [ :consumo| consumo cantConsumos: unDateLapse ]



Consumo >> cantConsumos: unDateLapse

( unDateLapse includesDate: fecha )

         ifTrue: [ ^consumoEnergiaActiva ].

^0