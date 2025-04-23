---
tags:
  - spd
  - unidad-6
  - tiempos
  - latencias
---
los procesos por los cuales las [[Memorias]] pueden leer o esribir datos requieren de ciertos tiempos por que nada es instantaneo , como el tiempo que le lleva a la memoria en seleccionar una celda o presentar un dato en el bus de datos y todo esta pautado por el pulso de clock.

- #### tiempo de acceso: 
	es el que se tarda la memoria en responder a un pedido de lectura hazta que el mismo queda satisfecho

- #### cycle time: 
	es el tiempo que transcurre desde un pedido hasta que se puede realizar otro, hasta que el primer pedido no quede satisfecho no se puede realizar/ejecutar otro

- #### write time: 
	el tiempo de escritura consta de dos tiempos 
	- **setup time**: 
		es el tiempo en el cual se le presentan los datos a la memoria previo la llegada de la señal de lectura
	- **hold time**: 
		es un timpo de espera, los datos deberan manerse un tiempo luego de la señal de lectura

- #### CAS: (column acces strobe)
	tiempo que tarda la memoria en colocarse sobre la columna seleccionada

- #### RAS: (row acces strobe)
	tiempo que tarda la memoria en colocars sobre una fila

- #### active
	tiempo que tarda la memria en activar un tablero

- #### precharge:
	tiempo que tarda la memoria en desactivar un tablero
	