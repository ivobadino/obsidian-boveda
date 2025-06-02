---
tags:
  - spd
---
1. formato de inctruccion para cada operacion de e/s
	1. lectrura de 16 bits sobre el puerto de 8 bits (FFh) : IN AX, FF
	2. lectura de 8 bits sobre un puerto de 16 bits (FFFFh): IN AX, FF
	3. lectrua de 16 bits sobre un puerto de 16 bits (FFFFh): MOV DX, FFFF -->> IN AX, DX
	4. lectrura de 8 bits sobre un puerto de 8 bits(FFh): IN AL, FF

2. la unidad de entrada/salida es:
	1. la que permite el intercambio de informacion entre la CPU y la MP con los dispositivos externos

3.  afirmaciones:
	1. en el mapeo a memoria, el procesador utiliza el mismo set de instrucciones para accesos a memoria y para las operaciones de E/S
	2. en el mapeo a memoria, los dispositivos de E/S y la memoria de encuentran en el mismo espacio de direccionamiento 
	3. en el mapeo aislado, el procesador tiene instrucciones dedicadas para operaciones de E/S
	4. en el mapeo aislado, el procesador tiene un espacio de direcciones separado para dispositivos de E/S

4. Esta estrategia para programar las interacciones con dispositivos de E/S
	1. dispara la operacion de E/S en el dispositivo y la interfaz de E/S en el dispositivo y la interfaz de E/S avisa cuando se ah completado la operacion y el resulatado esta listo: ==ASINCRONICA==
	2. Espera a que el dispositivo finalice la operacion de E/S para continuar la ejecucion del programa en curso: ==SINCRONICA==

5. Funciones generales de la unidad de  E/S
	1. control y temporizacion
	2. comunicacion con la CPU
	3. comunicacion con los dispositivos
	4. almacenaminto temporal de datos
	5. deteccion de errores

6. un dispositivo puede tener solo una direccion de E/S para cada puerto

7. nuestro procesador utiliza señal de M/!IO(Memory / Input-Output negado) para indicar a los buses que tipo de operacion se va a realizar con la memoria principal o con las unidade4s de E/S 

8.  en la atencion de dispositivos perifericos, la CPU detecta, de a uno a la vez; si un periferico requiere atencion. Si la necesita, ejecuta las acciones que le son solicitadas. Si no, continua verificando el siguiente dispositivo. En este caso, estamos en presencia de una gestion de atencion y prioridades ==CENTRALIZADA==

9.  Se desea realizar un programa que identifique si una impresora conectada al puerto paralelo le falta papel. Los datos son los siguientes:
	
	- Data Port = 03BCh / Status Port = 03BDh / Control Port = 03BEh
	- Port description:
	    - b7=Busy
	    - b6=Acknowledge
	    - b5=Paper Out
	    - b4=Select In
	    - b3=Error
	    - b2=!IRQ
	    - b1=b0=Reserved
	
	- INSTRUCCION 1: MOV DX, 03BD
	- INSTRUCCION 2: IN AL, DX
	- INSTRUCCION 3: AND AL, 20
	- INSTRUCCION 4: JNZ NoHayPapel

10. formato de instrucción para cada operación de E/S
		1. Escritura de 8 bits sobre un puerto de 16 bits (FFFFh) → MOV DX, FFFF --> OUT DX, AL,
		2. Escritura de 16 bits sobre el puerto de 8 bits (FFh) → OUT FF, AX,
		3. Escritura de 16 bits sobre un puerto de 16 bits (FFFFh) → MOV DX, FFFF --> OUT DX, AX,
		4. Escritura de 8 bits sobre el puerto de 8 bits (FFh) → OUT FF, AL
11. 