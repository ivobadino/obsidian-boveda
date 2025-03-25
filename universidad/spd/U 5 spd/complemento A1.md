---
tags:
  - spd
  - ALU
  - unidad-5
  - binario
---
![[UNIDAD ARITMETICO LOGIACA(ALU)#** complemento A1 **]]

al igual que en SyM los numeros positivos contienen en su codificacion la magnitud del numero que representan. En cambio los negativos no, para los negativos se les tiene que aplicar el Ca1, o en otras palabras el flipp.

## que es el complemento a1 o flipp?

es basicamete como lo dice la palabra flip es "dar vuelta" o cambiar el 1 por el 0 o viceversa
1 -> 0
0 -> 1

es decir que si tengo el ==0==0001100 que es =12
pero si tengo el ==1==0011110:
- podemos analizar en los primeros 7 bits de derecha a izquierda que tenemos el numero 30, si analizamos su magnitud
- pero como adelante tenemos el bit ==1== es un numero negativo al cual tenemos que aplicarle el Ca1
- si realizamos el flipp nos queda ==0==1100001 que nos daria 97 , es decir que ==1==0011110 es igual a ==97==

# rango de representacion

rango acotado por que al igual que en el convenio de signo y magnitud por que se utiliza el bit mas significativo para representar el signo del numero. Tambien se divide al rango en dos mitades para representar con una mitad a los negativos y con la otra se representa a los positivos.

![[Pasted image 20250324211813.png]]

al tener las dos mitades, volvemos a tener el problema del doble cero que aparecio en el SyM 
![[rangoca1.png]]

 <h1 style="color: red; background-color: blue; text-align: center; border: 2px solid 
; border-color: red; border-radius: 20px"><strong>ESTE METODO NO SIRVE PARA HACER CUENTAS</strong></h1>

 