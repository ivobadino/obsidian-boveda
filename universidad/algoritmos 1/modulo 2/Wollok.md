---
tags:
  - algoritmos1
---
# crear un nuevo proyecto

- desde power shell o git bash  posicionarse en la carpeta que se desea utilizar
- utilizar el comando `wollok init --proyect nombredeejemplo` para iniciar un nuevo proyecto

### proyecto game

para crear un proyecto con wollok game se tiene que utilizar el comando: 
	`wollok init --project juego-pepita --game`

### en vs code

en visual studio code para ver este proyecto  creado solo hay que abrir la carpeta donde fue guardado el proyecto

cualquier cosa revisar la [pagina oficial de wollok](https://www.wollok.org/getting_started/new_project/)


---

# definir un objeto

	object pepita { 
		var energia = 100 
		
		method volar() { 
			energia = energia - 10 
		} 
		method comer(cantidad) { 
			energia = energia + 2 * cantidad 
		}
	}

## accessors

Como vimos en el párrafo Estado de un objeto, no es aconsejable que quien use a pepita manipule directamente sus variables, sino que debe enviarle mensajes que accedan o modifiquen las referencias a los objetos que conoce. Para ello existe cierto tipo de mensajes llamados accessors, cuyo fin es publicar la referencia (getter) o modificar dicha referencia (setter)

	object pepita {
		 ... 
	// getter method energia() { return energia }
	
	// setter method energia(_energia) { energia = _energia } 

- El getter se define como un método de una sola línea, que devuelve algo. 5 de 12 Objetos 

- El setter no, es un método que modifica el estado interno del objeto, no tiene necesidad de devolver nada.

## referencias en wollok

wollok tiene dos maneras de definir #referencias 

1. con variables `var nombredeejemplo = ` que puede ser modificada luego

2. con constantes `const  nombredeejemplo =  que no puede ser modificada en ningun momento 


## relaciones bidireccionales

esto le permite a dos objetos relacionados conocerse 

	object juan { 
		var mascota 
		
		method mascota(_mascota) { mascota = _mascota } 
		
		} 
		
	object firulais { 
		var duenio 
		
		method duenio(_duenio) { duenio = _duenio }
		
		}

## compartir valores

simplemente le pasamos la misma referencia a ambos objetos

	object tefi {
		... 
		method jugarCon(_mascota) { ... } 
	} 
	
	object juan {
		 ... 
		 method alimentarA(_mascota) { ... } 
	 }


si les mandamos mensajes a los objetos:

 - tefi.jugarCon(firulais) 
-  juan.alimentarA(firulais)
