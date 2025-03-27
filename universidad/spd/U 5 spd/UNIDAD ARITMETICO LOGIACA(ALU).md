---
tags:
  - spd
  - binario
---
# que es ?

la unidad aritmetico logica o alu por sus siglas en ingles es un componente esencial en el prosesamiento de datos de nuestro procesador, es donde ocurren todos los calculos necesarios para el funcionamiento de nustra maquina.

esta totalmente relacionada con el [[sistema binario]] ya que es el idioma el cual entiende nuestra maquina por ende la ALU en la cual realiza operaciones aritméticas (como suma, resta, multiplicación y división) y operaciones lógicas (como AND, OR y NOT)como su nombre lo indica

Para poder entender como opera la alu y como opera tenemos que primero entender que numeracion entera o decimal utiliza. Existen distintas formas de enumeracion las cuales algunas sirven para calculos y otras no.

# enumeracion entera

## **[[numeros enteros con y sin signo]]**

enumeracion mas basica en la que la que la codificacion en binario en su totalidad es para la magnitud del numero.

## **números enteros con signo**

## **[[convenio de signo y magnitud]]**

en este caso como queremos representar números positivos y negativos no podemos utilizar la totalidad de los bits parta poder representar la magnitud del numero. El bit mas significativo es utilizado para representar el signo del numero

## **[[complemento A1]]**

es un método para representar números negativos en binario, donde se invierten todos los bits de un número (0s a 1s y viceversa). Aunque útil, tiene la desventaja de la doble representación del cero y ha sido ampliamente superado por el complemento a dos.

## **[[complemento A2]]** 

es el método estándar para representar números negativos en computadoras. Se obtiene invirtiendo los bits de un número y sumando 1, eliminando la doble representación del cero y simplificando las operaciones aritméticas.

## **[[convenio de exeso 2^(n-1)]]**

representa números desplazando el cero a la mitad del rango posible. Suma 2^(n-1) al número para codificarlo en binario, simplificando comparaciones pero requiriendo ajuste en operaciones aritméticas.

[[aritmetica y logica]]