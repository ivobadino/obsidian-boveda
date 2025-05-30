
1. indicar la representacion en IEEE 754sp 
	- los desnormalizados se normalizan con 0,xxx...............x
	- los normalizados se normalizar con 1,xxx....................x
	
2. identificar el comportamiento del contador de programa en cda situacion:
	- la instruccion contiene la direccion del objeto requerido para la ejecucion de la instruccion -> indireccion
	- el pc(contador de programa) incrementa de a 1 para proseguir leyendo la proxima posicion de memoria  -> habitual
	- la instruccion contiene el valor que tiene que colocarse en el contador de programa para proseguir con la ejecucion de la proxima instruccion -> salto
	
3. el contador de programa....
	- contiene la direccion de la proxima instruccion a ejecutarse
	
4. ciclo de instruccion de nuestro procesador visto:
	- instruccion fetch
	- instruccion decode
	- operand fectch
	- exclution
	
5. para cifras binarias expresadas en  ieee 754 
	1. NORMALIZADOS FINITOS 
		1.  exponente decimal menor = -126
		2. exponente decimal mayor = 254
		3. mantisa mas pequeña = 0
		4. mantisa mas grande = 11111111111111111111111
	2. DESNORMALIZADOS
		1. exponente decimal menor = -126
		2. exponente decimal mayor = 254
		3. mantisa mas pequeña = 00000000000000000000001
		4. mantisa mas grande = 11111111111111111111111
	
6. afirmacion correcta:
	1. en la segmentacion de intrucciones cada etapa de la cadena esta especializada en una tarea especifica y lleva a cabo siempre la misma actividad
	
7. pasar a punto flotante ieee 754 el decimal +132.8 con el menor error posible
	1. 4304CCCD
	
8. indicar para cada tipo de representacion ieee 754 considerar signo de la mantisa 
	1. infinitos  -->> 0...1 | 255 | 0,000...00
	2. quiet not a numer -->>  X | 255 | 1,1XXXX...X,
	3. signaling not a number -->> X | 255 | 1,0XXXX...X
	4. normalizados finitos -->> 0..1 | 1...254 | 1,XXXX...X
	5. ceros -->>  0..1 | 0 | 0,0000....0
	6. desnormalizados finitos -->>   0..1 | 0 | 0,XXXX...X