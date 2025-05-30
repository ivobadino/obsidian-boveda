---
tags:
  - spd
  - memoria
---
# [[Memorias|memoria]] cache

este tipo de memoria nace para incrementar la velocidad de transmicion de datos evitando que el cpu tenga que buscar los datos en la memoria ram, por que ya los tiene en la cahe. La cache tambien acelera estos tiempos por que es una memoria de alta velocidad y por su cercania entre el cpu a comparacion de la memoria principal.

cuando el cpu quiere acceder a una direccion de memoria con altisima probabilidad querra acceder a la siguiente contigua, por eso se guardan en la cache bloques de memoria.

su exito puede ser atribuido a la propiedad de localidad de referencia
acierto(hit): el procesador encuentra en la memoria cahe el dato que busca
falla(miss): el procesador no encuentra en la memoria cache el dato que busaca, debe buscarlo en la m.principal, y ese bloque de codigo es llevado a la cache por que seguro el cpu pedira la sigiente direcciond de memoria

la encargada de coordinar y realizar los pedidos de memoria y chequear si lo que el cpu pide esta en la cache es la MMU(memori managment uniti)

la forma de trabajar de la MMU es particular, por que hace dos cosas a la vez, cuando la cpu pide un dato la MMU lo busca tanto en cache como en la memoria principal, si lo encuentra en la cache, no envia el de la memoria principal, pero si no esta en cache , ya ahorro tiempo en ir a buscarlo a la memoria principal, y envia desde memoria principal, el bloque de datos. 

# organizacion de la cache

indica las reglas para copiar los datos de la memoria principal a la memoria cache, asi como tambien las reglas par alojar datos nuevos cuando la memoria cache esta llena
Se asumirá: 
- La memoria común tiene una capacidad de 2^m bytes 
- Se la divide en bloques consecutivos de b palabras 
- El tamaño del bloque es una potencia de 2 
- Se tendrá la cantidad de 2^m / b bloques

---
# organizacion asociativa

- La caché se divide en M cantidad de líneas o renglones.
    
- Cada renglón contiene:
    - Un bit de validez (B).
    - El número de bloque (N).
    - Los valores (V) almacenados del bloque de memoria principal.  
    
- ==Cualquier dato de cualquier dirección de la memoria principal puede ser almacenado en cualquier línea de la memoria caché.
    
- El microcódigo debe:
    - Calcular el número de bloque.
    - Buscar ese número de bloque en la caché.

- Esto implica circuitería adicional y algoritmos de búsqueda más sofisticados, lo que aumenta el costo.
    
- A cambio, ofrece la mejor proporción teórica de aciertos (hit rate)
la memoria principal tiene 2^n direcciones:siendo n la cantidad de bits del bus de addres

longitu de palabra de memoria: cuantos bits ocupa el dato en cada posicion de memoria

b longitud de bloque de memoria, cuantas posciciones de memoria principal ocupa un bloque

para calular el numero de bloque al que pertece una direccion de memoria, esta se divide por b(longitud del bloque) siendo el cosiente el numero de bloque
y el resto el offset dentro de ese bloque, es decir que si de resto nos da 3  y el bloque tiene una longitu de 4 el dato dentro del bloque se encuentra en la ultima casilla/direccion

la capacidad de la memoria principal es (2^n) * (longitud de palabra)

## ejemplo ejercicio:

addres: 6f752
LP: 1 byte (4 bits)
B: 512
n: 20bits (cantidad de bits del bus de addres)
cantidad de renglones de la memoria asociativa es de 16 renglones

- cual es la capacidad de la memoria principal ?
	(2^20) + 1 byte = 20 mb

- cual es la capacidad de la memoria cache?
	tenemos un bloque en cada renglon de la memoria 
	el bloque tiene 512 posiciones de memoria 
	entonces la memoria tiene:
		16 * 512 = (2^4) * (2^9) = 2^13 bytes=

-   
 



# organizacion de mapeo directo

- La caché se divide en M cantidad de renglones.
    
- Cada renglón contiene:
    
    - Un bit de validez (B).
    - Una etiqueta (E).
    - Los valores (V).
- Cada bloque de la memoria principal tiene asignado un único renglón en la caché.
    
- El número de bloque se calcula como: dirección / b (donde b es la cantidad de palabras por bloque).
    
- La etiqueta se calcula como: # bloque / Cantidad de renglones.
    
- El número de renglón se calcula como: # bloque mod Cantidad de renglones.
    
- No es necesario buscar en toda la caché para encontrar un bloque.
    
- La etiqueta resuelve el problema de mapear direcciones de memoria principal con el mismo número de renglón en la caché.
    
- Es más rápido y sencillo que la organización asociativa.

# comparacion

**1. Ubicación del bloque:**

- **Asociativa:** Un bloque de la memoria principal se puede ubicar en _cualquier_ línea de la caché.  
    
- **Mapeo Directo:** Cada bloque de la memoria principal solo se puede ubicar en _una única_ línea específica de la caché.  
    

**2. Búsqueda de bloques:**

- **Asociativa:** Se requiere buscar en todas las líneas de la caché para encontrar un bloque específico, comparando las etiquetas.  
    
- **Mapeo Directo:** La ubicación de un bloque se determina directamente por una función, por lo que no es necesario buscar.  
    

**3. Complejidad y costo:**

- **Asociativa:** Es más compleja de implementar, ya que requiere circuitería adicional y algoritmos de búsqueda sofisticados. Esto la hace más costosa.  
    
- **Mapeo Directo:** Es más simple de implementar, lo que reduce su costo.  
    

**4. Tasa de aciertos (hit rate):**

- **Asociativa:** Generalmente tiene una tasa de aciertos más alta debido a su flexibilidad en la ubicación de los bloques.  
    
- **Mapeo Directo:** Puede tener una tasa de aciertos más baja si hay muchos bloques que se mapean a la misma línea, lo que provoca conflictos y reemplazos frecuentes.
    

**5. Rendimiento:**

- **Asociativa:** Tiende a ser más lenta en la búsqueda de bloques debido a la necesidad de comparar etiquetas en todas las líneas.
    
- **Mapeo Directo:** Es más rápida en el acceso ya que la ubicación del bloque se calcula directamente.
    

En resumen:

- La **caché asociativa** es más flexible y generalmente ofrece un mejor rendimiento en términos de tasa de aciertos, pero es más compleja y costosa.
    
- La **caché de mapeo directo** es más simple y rápida, pero puede ser menos eficiente si hay muchos conflictos de mapeo.

---
# politicas de escritura a memoria principal

las politicas determinan como se administra la escritura de la memoria RAM comun con los datos contenidos en la memoria cache

- ## escrtitura a memoria (write - through cache)
	- cuando se modifica la cache se modifica el mismo dato en la memoria principal 
	- no tiene problemas de consistencia
	- beneficioso para procesos de lectura intendiva

- ## retrograbado (write - back cache)
	- se modifica solamente la cache
	- se modifica el dato en la memoria principal comun cuando se necesita desocupar un bloque de la cache que tiene datos modificados 
	- mas performante que el anterior
	- beneficioso para prosesos de escritura intensiva
	- es necesario usar 1 bit mas para indicar si el renglon de la cache fue modificado o no - dirty bit
- ¿que bloque saco para entre uno nuevo?
	- LRU (least recently used) - RANDOM - FIFO (first in first out)