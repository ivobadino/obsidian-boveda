---
tags:
  - spd
---

# SRAM
## static random acces memory

son memorias de lectura/escritura que mantienen sus datos siempre que tengan alimentacion, es decir que son volatiles. Estan construidas con flipp flops tipo D esto implica que son memorias de alta velocidad(devuelven un dato en 1ns). Esto a su ves implica que son memorias caras y que consumen mucha energia. Son memorias utilizadas en dispositivos que requieren alta velocidad de operacion como los procesadores o sistemas de procesamiento de imagenes. En estos dispositivos la SRAM se utiliza en registros o memoria cache.

***
# DRAM
## dynamic random acces memory

a diferencia de las memorias estaticas requieren de un pulso de refresco para mantener los datos. Esto sucede por como estan construidas, estan echas con capacitores, pero los capacitores al ser pequeños y no ser ideales se descargan con el tiempo entonces la memoria automaticamente le envia un pequeño pulso para que el capacitor no se descargue. Al tener este sistema ahorran mas energia / consumen menos que las SRAM . Esta memoria es mas lenta que la SRAM  pero es mas barata y consume menos energia. Se usan en memorias principales. pero al solo estar construidas con MosFET son mas chicas y tienen mas dencidad de integracion

***
# SDRAM
## synchronous dynamic random acces memory

permiten el acceso a un bloque de datos que esten en fila, haciendo una transferencia sincronizada. Esto quiere decir que cuando se haga el pedido de una direccion de memoria, la memoria no solo buscara esa direccion sino que tambien buscara las celdas siguientes(Una sola fila ), y la guardara. Esto permite la transmicion de datos en rafaga(burst) lo que permite tener una transmicion de datos mas rapida. Se envian primero la cantidad de datos a transferir, luego la direccion donde se comenzara a almacenar.  a partir de ahi se transfieren varios bytes por ciclo.

>> por que se transmiten los datos en rafaga sin crear problemas??. por que el procesador trabaja de forma secuencial y si pide una direccion de memoria lo mas probable es que pida la direccion de memoria contigua.

***
# DDR DRAM
## double data rate  dynamic random acces memory

fabricadas con tecnologia SDRAM pero transfieren los datos en ambos flancos del pulso de reloj. Es decir que en el pulso de clock tenemos el flanco asendente en el cual las memorias SDRAM comunes ejecutan la accion, pero en este caso las DDR actuan tambien en el flanco decendente, lo que permite duplicar la velocidad sin cambiar la tecnologia solo la forma de concetar los bancos de memoria(interleaving). Trabajan con menos voltaje(trabjan con 2.5 a comparmaracion de 3.3v). Poseen tecnicas avanzadas de optimizacion: 
	- interleaving
	- pipelining
el timpo de acceso no es siempre igual.
buffer inteerno de dos bits(prefetch buffer)
velocidades de buffer desde 200 mhz hasta 400 mhz
dimm de 184 contactos

## DDR2

- Duplican la velocidad del bus respecto de las DDR (533 MHz a 1 GHz) 
- El buffer de prefetch es de 4 bits 
- Tensión de trabajo de 1.8V 
- DIMM de 240 contactos 
- Tienen menor latencia que las DDR

## DDR3

- El buffer de prefetch es de 8 bits 
- Velocidad del bus de 800 Mhz a 2 Ghz 
- Tensión de trabajo de 1.5V 
- También el módulo DIMM es de 240 contactos pero se modifica la muesca 
- Tienen menor latencia que las DDR2!

## DDR4

- Duplican la velocidad del bus respecto de las DDR (2,13 GHz a 4,23 GHz) 
- El buffer de prefetch es de 4 bits 
- Tensión de trabajo de 1,2 a 1,05 V 
- DIMM de 288 contactos 
- No es compatible con las anteriores 
- Lanzada a finales de enero de 2014 
- Incremento del largo de la ráfaga de datos 
- Chequeo de paridad a nivel de bus de address y comandos

## DDR5

- Velocidad del bus 5,2 GHz o más 
- Tensión de trabajo de 1,1 V 
- 128 GB o más en una placa 
- Duplicarán ancho de banda de las DDR4 
- Se comercializará cerca de julio 2020

***
# XDR
## extreme data rate

es una version mejorada de la RAMBUS RDRAM 
permiten un ancho de banda mas alto que las DDR2 y GDDR4 
ideal para placas de video o consolas de videojuegos

# MRAM
## magnetoresistive RAM

usa discos ferrromagneticosseparados por una capa aislante en lugar de acumulacion de cargas electricas para guardar un bit 
tienen menos tiempo de acceso y menor consumo de memoria
menor densidad de memoria
no volatil