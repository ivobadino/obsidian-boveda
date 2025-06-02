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

El set de instrucciones son un conjunto de instrucciones disponibles para el programador, son codigos binarios asociados a un codigo simbolico como en nuestro caso a asemmbler . Que atara la ejecucion a un microprocesador por que la codificacion solo sera entedida por este.

---
# contador de programa 

contiene la proxima instruccion a ejecutar, es accesible al programador. Cuando se inicia la ejecución de un programa nuevo, se carga este registro con la dirección de la primera instrucción del programa en cuestión

## tiene tres modos de ejecucion.

- ## primer modo , modo habitual

	el pc se carga con la primera instruccion del programa, se lee y se incrementa en 1 para proseguir leyendo la proxima posicion de memoria

- ## segundo modo, modo salto

	se "rompe" el modo habitual de la ejecucion del programa por que se proceso que hay un salto, se debera continuar la ejecucion en una posicion distinta a la proxima .
	Se carga el contador de programa en forma directa y se continua con la ejecucion en modo habitual.

- ## tercer modo, modo de indireccion
	
	el objeto requerido no se encuentra ubicado a continuacion del que esta en ejecucion , se resuelve la indireccion y se carga el buffer de direccionamiento, la ejecucion del programa nos se altera, el PC no cambia


----
# ejecucion de instrucciones

## paralelismo

hay dos tipos de paralelismo  
### paralelismo temporal

solapar tiempos en un mismo dispositivo 
### paralelismo espacial

agregar mas dispositivos para trabajar al mismo tiempo


# ciclo de instruccion (IF ID OF EX)

- ## instruccion fetch (busqueda de instruccion)
	- 
- ## instruccion decode (decodificacion del codigo de operando)
	- 
- ## operand fetch (busqueda de los operandos u objetos restantes)
	- 
- ## execution (ejecucion de operando)
	- 

---
# pipelines

es una tecnica de ejecucion en paralelo donde multiples instrucciones se procesan al mismo tiempo pero en diferentes etapas. En cada detapa se realiza una accion con una instruccion y, una vez que terminan, cada etapa recibe la instruccion que termina de procesar la etapa anterior para seguir trabajando. cada etapa o segmento de la cadena esta especializada en una tarea especifica de la "linea de ejecucion" y lleva a cabo siempre la misma actividad. Esta tecnologia es propia de procesadores eficientes


# errores en los pipelines

## problemas de datos
## PROBLEMA DE DATOS: RAW(READ - AFTER - WRITE)
Un registro modificado, es leido inmediatamente luego. Como modificacion puede no haber finalizado, la lectura puede ser erronea.
	
		 MOV AX,BX
		 MOV [DS:0302]

## PROBLEMA DE DATOS: WAR(WRITE - AFTER - READ)
similar a la anterior peor alterando la lectura por modificaciones y viceversa

		MOV SI, AX
		MOV AX, [BX + 20h]

## PROBLEMA DE DATOS: WAW (WRITE - AFTER - WRITE)
se ejecutan dos intrucciones que escriben el mismo operando. La primera puede terminar luego de la segunda

		MOV DX, 200h
		LEA DX, datonuevo


## PROBLEMAS DE CONTROL: SALTOS CONDICIONALES
Ocurren cuando una instrucccion de salto debera ejecutarse, pero no se puede saber si la condicion de salto sera satisfactoria con lo cual la proxima instruccion a ejecutar no es la que fisicamente esta a continuacion del salto.

## PROBLEMA ESTRUCTURAL: NECESITO MAS HARDWARE
Ocurre cuando dos o mas instruccines requieren una misma unidad estructural como la ALU

		ADD AX, BX
		MUL CX

## SOLUCION AL PROBLEMA DE DATOS
Se envia el dato necesario de manera anticipada, sin esperar a que se actualize el registro final. Lo manda antes, desde la etapa donde la isntruccion accede a la memoria (MEM - MEMORY ACCEES) a donde se lo quiera.

## SOLUCION AL PROBLEMA DE CONTROL(prediccion de saltos): 
Se bada en poder determinar si una condicion de salto (o division en dos ramales) en el flujo de isntrucciones se ejecutara o no para permitirle a la CPU encontrar y ejecutar instrucciones sin tener que esperar para que se resuelva la condicion de dalto. Estos predictores se utilizan en arquitecturas con pipeline, con lo cual evitan que el pipeline de instrucciones se vacie. Existen mas de un tipo de predictor de salto:
- ### ESTATICO:
	- no se basa en la dinamica del codigo, solo de la instruccion aislada, por lo que predice que el saltyo no va a courrir y continua con la instruccion siguiente. Cuando condicion de salto es evaluada y si se da, continua la ejecucion de la direccion de salto otros asumen que los saltos "hacia atras" ocurrira mientras que los saltos hacia adelante no lo haran ; efectivos para loop
- ### DINAMICO
	- Se basa en una larga lista de historia de saltos para ser más preciso, guardando bits para indicar si en el pasado se ejecutó el salto o no; se basa en conceptos neurales. Se utiliza dos bits para historia de saltos; si una predicción se cumple, se mantiene la predicción; si no se cumple por primera vez, lo registra, pero mantiene

## SOLUCION AL PROBLEMA DE ESTRUCTURA:
Se agrega más estructuras. Si, por ejemplo, tengo que realizar dos instrucciones en donde debe intervenir la ALU, debiera esperar a que finalice la primera para poder ingresar la segunda; por ello, se pueden integrar en lugar de una ALU, dos ALU.


# super pipeline
