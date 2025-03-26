---
tags:
  - spd
  - ALU
  - unidad-5
  - binario
---
# concepto de overflow

cualquier cifra que caiga fuera de mi rango de representacion va a entrar dentro del overflow (fuera de flujo). ==Va a haber un desbordamiento==

### mi rango de Ca2:
![[Pasted image 20250324223025.png]]

la operacione esta fuera del rango de representacion.

## si hay overflow
en el caso de que se de el caso del overflow, es decir que el resultado de una operacion se exeda del rango de representacion, en el procesador se encendera una bandera o flag llamada "carry flag" o bandera de acarreo. 

#### suma binaria de enteros **sin signo**

si CF=1 hay overflow y en el debug se muestra como "CY"
y si CF=0 no hay overflow y en el debug se muestra como "NC"

#### suma binaria de enteros **con signo**

el carry ya no importa por que hay sumas de numeros con signo que no dan carry y aun asi estan incorrectas. Para este caso se usa otra flag, la overflow flag "OF"

si OF =0 el resultado es correcto, en el debug veremos NV
si OF =1 el resultado es incorecto, en el debug veremos OV


en las operaciones con signo el pedir prestado o "borrow" activa el carry flag. y eso significaría que la operación esta correcta 

pero en una operación sin signo la operación seria incorrecta al haber un 1 en el carryflag. por que se salio de rango

si el reultado de una operacion arroja un numero con el bit mas significativo en 1, el "sign flag" SF=1 indicando que es negativo. en caso contrario dara SF=0

el sf en el debug si es =0 es PL , si es =1 es NG

### Sin Signo: 
- Carry o Borrow (pedir prestado) implican Overflow  

### Con Signo: 
- Se ignoran el Carry o Borrow
- OverFlow SIEMPRE!:
	- Positivo + Positivo = Negativo 
		- (positivo – negativo = negativo) 
		
	- Negativo + Negativo = Positivo 
		- (negativo – positivo = positivo) 
		
- OverFlow NUNCA!: 
	- Positivo + negativo (positivo – positivo) 
	- Negativo + positivo (negativo – negativo)


## sumador aritmetico

| A   | B   | s   | Yc  |
| --- | --- | --- | --- |
| 0   | 0   | 0   | 0   |
| 0   | 1   | 1   | 0   |
| 1   | 0   | 1   | 0   |
| 1   | 1   | 0   | 1   |

![[Pasted image 20250326142615.png]]


# sumador / restador

para restar dos numero positivos, no toca hacer :
- en primer lugar plantearnos la operacion : A + B
- por matematica sabemos que A + B es igual a hacer A + (-B)
- sabemos que -B es lo mismo que el Ca2(B)
- que es lo mismo que Ca1(B) + 1
- entonces hacer A - B es lo mismo que hacer : a + Ca1(B) + 1

![[Pasted image 20250326152053.png]]


# multiplicacion binaria

la multiplicaciones una susesion de sumas y desplasamientos 