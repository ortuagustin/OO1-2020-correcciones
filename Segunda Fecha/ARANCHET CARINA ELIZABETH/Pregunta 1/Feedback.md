La solución es correcta.

Como mejora, se podría haber llevado esta expresión (de Usuario>>consumoMaximo: unDateLapse)

total:=consumos select:[:aux|aux unDateLapse includesDate:fecha]

A un método de usuario:

Usuario>>consumosEn: unDateLapse
  ^ consumos select: [:consumo | unDateLapse includesDate: consumo fecha]

Usuario>>mayorConsumo:unDateLapse
^ (self consumosEn: unDateLapse)
    sumNumbers: [:consumo | consumo consumoEnergiaActiva ]


Corrigió Agustín Ortu