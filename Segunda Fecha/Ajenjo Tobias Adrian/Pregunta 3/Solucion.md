Distribuidora>>usuarioConMayorConsumoDurante:unDateLapse

^usuarios detectMax:[:u | u mayorConsumo:unDateLapse ].



Usuario>>mayorConsumo:unDateLapse

| enFecha |

enFecha:=consumos select: [:consumo | unDateLapse includesDate:consumo fecha].

^enFecha sumNumbers:[:cons | cons consumoEnergiaActiva]





Consumo>>fecha

^fecha





Consumo>>consumoEnergiaActiva

^consumoEnergiaActiva