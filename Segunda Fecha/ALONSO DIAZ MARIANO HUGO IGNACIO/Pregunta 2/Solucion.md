Object subclass: ClienteDeCorreo

v.i: carpetas inbox

ClienteDeCorreo >> initialize

carpetas:= OrderedCollection new.



ClienteDecorreo >> carpetasPesadas

^carpetas collect: [ :carpeta | carpeta calcularTamanioEmails ]





Object subclass: Carpeta

v.i: emails



Carpeta >> initialize

emails:= OrdererCollection new.



Carpeta >> calcularTamanioEmails

"Asumo que #calcularTamanio devuelve la cantidad en Bytes que pesa la carpeta y lo comparo con 1.048.576 que es el equivalente a 1MB.



emails reject: [ :email | email  calcularTamanio < 1048576 ]









Object subclass: Email

v.i: adjuntos

Email >> initialize

adjuntos:= OrderedCollection new.



Email >> calcularTamanio

"Asumo que el mensaje #tamano enviado a los elementos de la clase Archivo en la colección devuelven el tamaño en bytes del mismo, por otra parte decidí utilizar el mensaje #sizeInMemory porque retorna el tamaño en bytes de la variable indicada del receptor en este caso"



| var |

var := adjuntos sumNumbers: [ :adjunto | adjunto tamano ].

^ self titulo sizeInMemory + self cuerpo sizeInMemory + var