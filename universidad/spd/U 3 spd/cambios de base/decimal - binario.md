---
tags:
  - decimal
  - binario
  - spd
  - unidad-3
---
# **decimal a binario**
## en que consite ??

consite basicamente en la sucesiva divisiones del numero #decimal por la base, esto es caracteristico del [[cambio de base]] de decimal a cualquier tipo de base. Pero al estar operando con #binario y #decimal utlizamos la base 2 y la 10 respectivamente. Existen dos formas de realizar este cambio de base

## primera forma : divisiones sucesivas 

- en primer lugar agarramos al numero decimal y lo dividimos por la base elegida(en este caso 2)
- realizamos una división entera de la cual vamos a obtener un resto entero, y un cociente 
- a este cociente le volvemos a aplicar una divicion por 2
- iteramos esta accion hasta llegar que el cociente termine siendo 1 o 0
- luego para formar el numero binario agarramos los restos de las diviciones de derecha a izquierda

![[Pasted image 20250322173004.png]]


## segunda forma: restas sucesivas

esta forma es mas practica y se puede realizar mentalmente mas facil pero **PERO NO ES RECOMENDABLE** . utilizamos las potencias de 2

- Anotar las potencias de 2, de derecha a izquierda, hasta que la potencia supere el valor de la cifra decimal. Esa última, no colocarla. 
- Comenzar de derecha a izquierda, es decir, de la posición de más peso.  
- Restar las potencias de 2 de la cifra decima sucesivamente, siempre que el resultado sea positivo, hasta llegar a 0 (cero). 
- Cada vez que se pueda restar una potencia de 2, colocar un “1” en esa posición. Si no se puede, se coloca un “0”.

![[Pasted image 20250322174230.png]]


# **binario a decimal**
## **Método paso a paso:**

1. **Asigna valores posicionales:**
    - Comienza desde el dígito binario más a la derecha.
    - Asigna a cada dígito un valor posicional que es una potencia de 2, comenzando con 2⁰.
    - Avanza hacia la izquierda, aumentando el exponente de 2 en 1 para cada dígito.
2. **Multiplica cada dígito por su valor posicional:**
    - Multiplica cada dígito binario (0 o 1) por su correspondiente valor posicional (potencia de 2).
3. **Suma los resultados:**
    - Suma todos los resultados obtenidos en el paso anterior.
    - El resultado final es el equivalente decimal del número binario.

## forma simplificada

- a cada digito empezando de derecha a izquierda le asigmanamos una potencia de dos en orden (1, 2, 4, 8 ,16, 32, 64, 126, 512, 1024, 2048, etc)
- luego agrupamos las potencias de los digitos "1"
- sumamos dichas potencias y obtenemos el numero #binario y #decimal

[[cambio de base]]