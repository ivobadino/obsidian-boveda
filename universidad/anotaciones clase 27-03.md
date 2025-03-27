---
tags:
  - spd
  - unidad-6
---

# clase 26-03
# spd
# flip-flops

son dispositivos que nos permiten almacenar un bit (1 || 0)

su diagrama es:
![[insertar imagen del flip flop]]

donde: 
- **LA ENTRADA D**(entrada sincronica):es la entradad donde recibe los datos
- **SEÑAL DEL CLOCK**: es de suma importancia ya que es la señal que le dice al fip-flop que tiene que guardar el valor de "D" en ese momento
- **SALIDA Q**:
- **SALIDA !Q**:
- ### SEÑALES ASINCRONICAS:
  - **SEÑAL SET**:Coloca Q en 1 en forma asincrónica
  - **SEÑAL CLEAR**:Coloca Q en 0 en forma asincrónica

---

# buses

## bus de direcciones

en nuestro computador tenemos 16 registros. esto quiere decir que para direccionar a caulqueira de estos necesitamos solamente ==4== bits. Esta informacion corre por el bus de addres o direcciones en español.

para direccinar a cada registro necesitariamos un decodificasdor de 4 bit con 16 salidas.

## bus de datos

para presentar los datos de un registro tengo que tener entradas/salidas controladas desde y hacia el bus de datos donde pasan todos los datos, tanto de escritura como los de lectura. Para ello necesito controlar la entrada y salida con buffers controlados por el **bus de control**

## bus de control

es un bus el cual indica si los datos se leen o se escriben

## en conjunto

### secuencia de lectura/escritura
1. xd
2. xd
3. xd


---

# clase 27-3
# algoritmos 1