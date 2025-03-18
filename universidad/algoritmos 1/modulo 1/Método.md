---
tags:
  - metodo
  - objeto
  - mensaje
  - propiedad
  - algoritmos1
---
# que pasa cuando un objeto recibe un mensaje?

este mensaje ejecuta un pedaso de codigo, o si lo queremos ver como algo ya conocido, ejecuta una "funcion", que le permite al objeto realizar alguna accion. Este codigo se llama metodo, el cual contiene toda la logica y procesos para que este metodo ejecute alguna accion.

### que es un metodo

- es el comportamiento de un objeto
	- Un método define las acciones que un objeto puede realizar.
	- Es la forma en que un objeto interactúa con el mundo exterior y responde a los mensajes que recibe.
	
- tienen manipulacion  de atributos
	- Los métodos pueden acceder y modificar los atributos de un objeto.
	- Esto les permite cambiar el estado interno del objeto y realizar operaciones basadas en sus datos.
	
- tienen funciones asociadas a objetos
	- A diferencia de las funciones independientes, los métodos están vinculados a objetos específicos.
	- Esto significa que un método solo puede ser invocado por un objeto de la clase a la que pertenece.

### caracteristicas de un metodo

- **Nombre:**
    - Cada método tiene un nombre único que lo identifica.
	
- **Parámetros (opcional):**
    - Los métodos pueden recibir parámetros, que son valores que se utilizan para realizar la acción.
    - Los parámetros permiten que los métodos sean más flexibles y adaptables.
	
- **Valor de retorno (opcional):**
    - Los métodos pueden devolver un valor como resultado de su ejecución.
    - El valor de retorno puede ser de cualquier tipo de dato.

## disparadores

los metodos tiene dos formas de "dispararse", en si son dos instrucciones, [[Mensaje| mensajes]], pero uno es una instruccion directa la otra esta dentro de una pregunta 
- ### instrucciones 
	 este mensaje disparador es directo y le dice al objeto que realize una accion concreta ej: cohete, despega --> starship.launch()  --> el cohete levanta vuelo
- ### preguntas
	este mensaje disparador es menos directo y de el cual el metodo nos devuelve información ej: cohete cual es tu altitud?? --> starship.altitude() --> 10km