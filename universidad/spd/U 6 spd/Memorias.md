---
tags:
  - spd
  - unidad-6
  - memoria
---

## que son?

son dispositivos para almacenar datos. Estos datos son en formato digital, es decir en ceros y unos. Estos datos son simplemente codigos binarios que son dificiles de interpretar si no sabemos a que hacen referencia. El significado se los da el usuario.

## caracteristicas:

nos permiten diferentes caracteristicas a cada tipo de memoria

- #### **capacidad:**  
	- nos indica la cantidad de datos que pueden almacenar y esta medida en  bits, bytes o múltiplos (KB, MB, GB, TB).
- #### **Volatilidad:**
	- Si la información se mantiene al interrumpirse la energía (no volátil) o se pierde (volátil).
- #### **velocidad de acceso**
	- es el tiempo que se tarda en leer o escribir un dato, esta caracteristica es fundamental en el rendimiento del sistema
- #### **Tecnologia de implementacion:** 
	-  se refiere a los tipos de circuitos que la componen y las tecnologias utilizadas


## jerarquia de memorias
van desde las memorias mas caras, rapidas y con menos almacenamiento hasta las memorias mas baratas, lentas y con mas capacidad
de almacenamiento.

- [[registros]] (0,3 ns)
- cache
	- cache L1 (1 ns)
	- cache L2 (2,8ns)
	- cache L3 (13ns)
- memoria principal (100 µs)
- discos de estado solido (µs)
- discos rigidos (8 ms)
- discos opticos (40 ms)
- cintas magneticas 
---
# por que acceso aleatorio

que una memoria sea de acceso aleatorio o random, nos dice que la CPU puede acceder a cualquier ubicación de la memoria **directamente**, sin tener que pasar por ubicaciones intermedias. Es como poder abrir un libro en cualquier página instantáneamente, en lugar de tener que pasar por todas las páginas desde el principio para llegar a la que quieres.

## Ordenamiento

no es mas que la forma en que se guardan datos de distintas longitudes de palabra con respecto a la longitud de palabra de la memoria involucrada.

es decir que si nuestro dato es de 16 bits y nuestra memoria almacena de a largos de palabra de 8 bits, la logica de control va a tener que dividir la palabra en dos y guardarla en dos celdas distintas pero contiguas. Esta divicion de palabra en datos de 16 bits la podemos ver mejor en un registro como puede ser **AX** el cual esta divicion se realizaria con ==**ah**== y ==**al**==. pero ahora nos encontramos con una pregunta **que parte de la palabra guardo primero??primero al o ah?**. para esto existen dos tipos de ordenamiento:

![[Pasted image 20250420182659.png]]

- ### Ordenamiento little endian (intel):
	este ordenamiento es el mas utilizado, el cual primero en la posicion de memoria N guarda el L.S.Byte (Less significant byte), el byte menos significante(AL). seguido en la posicion de memoria N+1 el M.S.byte (more significant byte), el byte mas significativo(aH).

- ### Ordemaniento big endian (motorola) 
	este ordenamiento se utilizaba en los procesadores de motorola, no es practicamente usado en la actualidad. Pero consistia en lo opuesto al little endian y guardaba en la posicion de memoria N el byte mas significativo (MSByte) y en la posicion de memoria N+1 se guardaba el byte menos significativo(LSByte).

