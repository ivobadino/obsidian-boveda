---
tags:
  - spd
  - unidad-6
---
# que son ?

son dispositivos electronicos con la capacidad de almacenar informacion en forma de bits. Estan compuestos por elementos mas pequeños, llamdaos flip-flops o biestable "D" . estos dispositivos individualmente solo pueden almacenar un 1 o un 0 pero su velocidad es la mas rapida de la jerarquia de memorias.

el flip flop consta de una entrada nombrada "D" y una salida nombrada "Q". el funcionamiento del flip flop es sencillo: La salida "Q" toma el valor de la entrada "D" cuando se produce un pulso de reloj, En otras palabras, el flip-flop "captura" el valor de la entrada "D" en el momento en que llega la señal de reloj y lo mantiene hasta el siguiente pulso de reloj.

la señal del reloj es fundamental en el funcionamiento del flip flop  ya que es el que determina el cambio de estado de este.

entonces los registros son dispositivos que almacenan informacion de forma temporal. y la cantidad de bit que son capaces esta dada por la cantidad de flip flops que contenga el registro.

## como esta compuesto un flip flop
![[Pasted image 20250403191547.png]]
**esta compuesto por las siguientes entradadas/salidas o conesxiones:** 
- D = Entrada sincrónica 
- Q y Q = Salidas 
- CLK = Señal de clock 
- SET = Coloca Q en 1 en forma asincrónica 
- CLR = Coloca Q en 0 en forma asincrónica

para guardar un dato existen dos formas:
- asincronicamente:
	- el pulso de reloj no tiene relevancia ya que hay un valor de 1 en set o en clr
	- Guardar un “1” → SET = 1 y CLR = 0
	- Guardar un “0” → SET = 0 y CLR = 1
- sincronicamente:
	- el reloj si tiene relevancia
	- set y clr estan en 0
	- Coloco en la entrada D el valor que quiero guardar
	- Coloco un pulso en la entrada CLK


# tipos de registros:

en esta materia veremos dos tipos de registros:
- ## [[registros de lectura-escritura]]
	-  son registros los cuales almacenan informacion para que sea procesada
- ## [[registros de desplazamiento]]
	- son registros los cuales son usados para hacer operaciones de producto y cociente