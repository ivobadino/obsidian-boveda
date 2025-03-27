---
tags:
  - spd
  - ALU
  - unidad-5
  - binario
---
![[UNIDAD ARITMETICO LOGIACA(ALU)#** complemento A2 **]]

este metodo consite en agarrar un numero positivo binario el cual quisieramos representar como negativo. le aplicamos el complemento a1, es decir intercambiar los ceros por unos y viceversa.
Luego de hacer el  flipp le sumamos un "1" binario al resultado del ca1. 
Esto nos va a dar el numero inicial pero convertido a negativo con complemento a2

### ejemplo con 4 bits:

- tenemos el numero 3 en binario: 0011
- le aplicamos el complemento a1: 1100
- le sumamos un 1: 1101

y ahi ya tenemos el numero 3 en negativo.

esto nos sirve para hacer restas  ej: 3 + (-3)

0011 +       ->         3 
1101          ->         -3
=               ->          =
0000          ->          0
## rango de representacion

el rango del complemento a2 es reducido ya que como los convenios anteriores sacrifica el bit mas significativo para representar el signo del numero. devido a como esta implementado este metodo, ya no tenemos dos ceros, tenemos uno solo.

![[Pasted image 20250324223016.png]]

 <h1 style="color: green; background-color: red; text-align: center; border: 2px solid 
; border-color: green; border-radius: 20px">ESTE METODO<strong> SI</strong> SIRVE PARA HACER CUENTAS</h1>

 