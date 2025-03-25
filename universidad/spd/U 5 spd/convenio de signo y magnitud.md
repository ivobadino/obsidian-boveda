---
tags:
  - spd
  - ALU
  - binario
  - unidad-5
---
![[UNIDAD ARITMETICO LOGIACA(ALU)#** convenio de signo y magnitud **]]

con N bit se pueden representar 2^N combinaciones posibles pero en este convenio el bit mas significativo se utliza para la representacion del signo.

#### por que el signo mas significativo??
en primer lugar no podemos elegir los bits del medio del numero. Es decir que si tenemos un numero de 4 bits, no podemos utlizar los bits 2 y 3 para representar el numero por que interfieren con la lectura de la magnitud del numero. 
y en segundo lugar no se puede por que complicaria los calculos
## rango de representacion 

dado que tenemos numeros negativos y positivos el rango de representacion se divide en dos mitades iguales,  una mitad negativa y una mitad positiva. Y a su vez  hay un bit menos de representacion de la magnitu ya que este esta destinado a a la representacion del signo.

![[Pasted image 20250324183045.png]]

esto quiere decir que contamos con 2^(n-1) valores positivos y 2^(n-1) valores negativo. el problema es que en este metodo de enumeracion nos encontramos con la problematica de que tenemos dos ceros: -0 y +0.

![[Pasted image 20250324202657.png]]

 <h1 style="color: red; background-color: blue; text-align: center; border: 2px solid 
; border-color: red; border-radius: 20px"><strong>ESTE METODO NO SIRVE PARA HACER CUENTAS</strong></h1>

 