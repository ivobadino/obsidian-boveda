---
tags:
  - spd
  - unidad-7
---
# QUE SON LAS MICRO INSTRUCCIONES?

Es un conjunto de bits de control que al ser activados, generan señales electricas necesarias para activar o desactivar componentes especificos de la CPU.

---
# SECUENCIAMIENTO

## Secuenciamiento implicito
### QUE ES ??

Es una forma en la cual las microinstrucciones estan guardadas en la memoria fisica. En este caso se encuentran de forma contigua de forma que para acceder a la siguiente micro instruccion solamnete se necesita un incrementador, al cual se le ingresa la direccion de memoria que contiene la microinstruccion en curso y al incrementarse en uno la direccion de memoria se accede a la siguiente microinstruccion

## Secuenciamineto explicito
### QUE ES ??

Es otra forma en la cual las microinstrucciones se almacenan, en este caso las microinstrucciones estan desordenadas dentro de la memoria, pero cada micro instruccion ademas de tener su propia direccion de memoria tienen la direccion de memoria de la siguiente instruccion a ejecutar.

---
# instrucciones

## set de instrucciones

el formato que tienen consiste en un primer paquete de bits que define la operacion (COP = codigo de operaciones). Y luego una serie de paquetees de bits (OBJETS) con la informacion complementaria para completar la operacion.

El set de instrucciones son un conjunto de instrucciones disponibles para el programador, son codigos binarios asociados a un codigo simbolico como en nuestro caso a asemmbler .
