---
tags:
  - spd
  - unidad-6
---
# que es ?

La [[MEMORIAS|memoria]] principal es un dispositivo conectado y contrlads directamente po la CPU. Es un dispositivo de almacenamiento de datos. Es una memoria volati, lo que quiere decir que precide de energia,  esto hara que al apagar el computador se borren los datos que esta contiene.

- Se organiza en "palabras" de _n_ bits, accediéndose a cada palabra individualmente mediante una dirección única de _p_ bits.  
    
- Almacena datos como ceros y unos, cuya interpretación depende de quién los utiliza.  
    
- Utiliza un ==**decodificador**== para seleccionar la palabra de memoria específica a la que se accede.  
    
- Contiene una ==**Matriz de Celdas de Memoria**== para el almacenamiento físico de los bits.  
    
- Incluye ==**Lógica de Control**== para gestionar las operaciones de lectura y escritura.  
    
- Emplea ==**Transductores**== para adaptar los niveles de señal entre el bus de datos y las celdas de memoria.

## estructura basica de una memoria principal

![[Pasted image 20250421164619.png]]

### bus de control 

- CS: chip select, si tengo mas de un chip de memoria selecciona cual se escribe/ lee, si tengo 2 chips tengo 16 direcciones 8 en c/u el chip alterna cual esta seleccionado
- OE: output enable, si quiero mostrar un dato de la memoria en el bus de datos , este se activa para mostrar los datos 
- WE: write enable, si quiero escribir un dato en la memoria del bus de datos este se tiene que activar
- R/¬W: ademas de las instrucciones de control OE y WE , necesito del read/No write, para poder leer o escribir los datos en la memoria , esta instruccion de control es la que le permite a la memoria leer o escribir , siendo las otras dos anteriores las que permutan las conecciones con el bus de datos para la lectura y escritura
- CLK

### bus de direcciones
en el 8086/88 tengo 20 bits de addres , es decir que tengo 2 a la 20 posiciones , es decir que tengo un mega de direcciones.

## entrelanzamiento interleave

es la forma de direccionar la memoria entre una cantidad n de bancos de memoria, de las cuales existen dos formas:
- **consecutivas** : lo que hace es seleccionar un banco hazta llenarlo de datos y solo ahi salta al siguiente, esto se consigue utilizando los bits mas significativos para el direccionamiento del banco y los menos significativos para la seleccion de la celda de memoria
- **separadas**: lo que hace es seleccionar los bancos de forma intercalada, esto se logra utilizando los bits menos significativos de la direccion de memoria para seleccionar el banco de memoria y los bits mas significativos para seleccionar la celda de memoria


