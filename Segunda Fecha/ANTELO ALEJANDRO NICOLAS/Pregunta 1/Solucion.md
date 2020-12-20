Object subclass #ClienteDeCorreo

v.i: carpetas


>> carpetasPesadas
^ carpetas collect: [ :carpeta | carpeta emailsUnMega]




Object subclass: Carpeta
v.i: emails


>> emailsUnMega

^ emails allSatisfy: [:email | email peso]




Object subclass: email
v.i: adjuntos

>> peso

^ ((adjuntos sumNumbers: [:archivo | archivo tamano]) + self titulo size + self cuerpo size) > 1)