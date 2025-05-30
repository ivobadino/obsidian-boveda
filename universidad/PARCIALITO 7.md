---
tags:
  - spd
---
1. en la ==SEGMENTACION== de instrucciones , cada etapa o segmento de la cadena esta ==ESPECIALIZADA== en una tarea ==ESPECIFICA== de la "la linea de ejecucion" y lleva a cabo ==SIEMPRE LA MISMA ACTIVIDAD==

2. indicar como se solucionan los problemas de los pipelines:
	1.   cmp ax,0
		jne otro:
		==PREDICTORES==
		
	2.  add ax, bx
		mul cx
		==AGREGAR ESTRUCTURA==
		
	3.   mov ax, bx
		mov [ds:0302],ax
		==FORWARDING==

3. indicar el tipo de problema para cada caso:
	1. se ejecutan dos instrucciones que escriben el mismo operando. la primera puede terminar luego de la segunda -->> WAW
	2. un registro leido es modificado inmediatamente luego. como la lectrura puede no haber finalizado, la modificación puede ser erronea -->> WAR
	3. Un registro modificado, es leído inmediatamente luego. Como la modificación puede no haber finalizado, la lectura puede ser errónea -->> RAW

4. tipo de predictor
	1. Se basa en una larga lista de historia de saltos → Dinámicos,
	2. No se basan en la dinámica del código, solo de la instrucción aislada. Simplemente predicen que el salto no va a ocurrir, con lo cual continúan con la instrucción siguiente → Estáticos

5.  ¿Cuáles instrucciones de salto de nuestro procesador de estudio podrán ocasionar un problema en los pipelines?
	1. JGE
	2. JB
	3. JZ
	4. JC
	5. JNZ

6. caracteristicas del acceso a memoria
	1. Cada procesador tiene un espacio propio de memoria que no comparte con otros procesadores,
	2. Se utiliza el caché L3 para compartir entre todos procesadores y los niveles L2 y L1 son propios,
	3. Esto evita que los datos compartidos circulen por los buses ya que están en el L3,
	4. Coherencia de caché entre todos los niveles

7.  las tablas de reserva se utilzan para identificar las direccines de memoria cache que se requieren para la ejecucion de los codigos de opreacion junto con sus objetos u operandos