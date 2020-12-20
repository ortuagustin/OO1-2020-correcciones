La solución es correcta.

Como mejora, se podría haber llevado esta expresión (de Usuario>>mayorConsumo: unDateLapse)

enFecha:=consumos select: [:consumo | unDateLapse includesDate:consumo fecha].

A un método de usuario:

Usuario>>consumosEn: unDateLapse
  ^ consumos select: [:consumo | unDateLapse includesDate: consumo fecha]

Usuario>>mayorConsumo:unDateLapse
^ (self consumosEn: unDateLapse)
    sumNumbers: [:cons | cons consumoEnergiaActiva ]


Corrigió Agustín Ortu