---
tags:
  - primer-curso
  - comentarios
  - operadores
  - convenciones
---
# anotaciones de [[JAVA primer curso]]
## comentarios

para usar comentarios podemos utilizar `//` si es un comentario de una sola linea 

```java
// ejemplo de comentario en java
```

para comentar un bloque entero de codigo utilizamos `/**/`

```java
/*Esta es la clase principal de la aplicación.
Contiene el método main. */ 
	public class MiClase { /** Este es el método principal que se ejecuta al iniciar la
	aplicación. @param args Un array de strings que contiene los argumentos de la
	línea de comandos. */ 
	public static void main(String[] args) {
	   System.out.println("¡Hola desde Java!"); 
	   
	   } 
	}
```

---
## operadores

### operador de asignacion

o mejor conocido como el " ==**=**== "

el cual sirve para asignarle o "guardarle " un valor de cualquier tipo a una variable, SII el valor corresponde con el tipo de variable al que es asignado, pero tipos de variable veremos mas adelante.

```java
int valor =  5;  //Atribuye el valor 5 a la variable valor 
```

También existen operadores de asignación combinados, que son una forma abreviada de asignación. Por ejemplo, el operador `+=` agrega un valor a una variable existente

```java
int valor =  10; 
valor += 15;  //Equivalente al valor = valor + 15, atribuye el valor 15 a la variable valor
```

## operadores aritmeticos

- `+` adicion
- `-`substraccion
- `*`multiplicacion
- `/`divicion
- `%`modulo o resto de la divicion

sirve para operar valores numericos y realizar calculos.

```java
int a = 10 + 5; // Atribuye el valor 15 a la variable a
int b = 10 - 5; // Atribuye el valor 5 a la variable b
int c = 10 * 5; // Atribuye el valor 50 a la variable c
int d = 10 / 5; // Atribuye el valor 2 a la variable d
int e = 10 % 3; // Atribuye el valor 1 a la variable ya que (el resto de la divición de 10 por 3 es 1)
```

## operadores relacionales

- `==` igual a
- `!=` diferente a
- `>` mayor a
- `>=` mayor o igual a
- `<` menor a
- `<=` menor o igual a 

```java
int a = 10; // Atribui o valor 10 à variável a
int b = 5; // Atribui o valor 5 à variável b
int c = 30; // Atribui o valor 30 à variável c

boolean igual = (b == a); //En este caso la variable igual quedará con valor *false, pues el el valor de b no es igual al valor de a.

boolean diferente = (b != c); //La variable diferente quedará con el valor de *true*, pues el valor de b es diferente del valor de c.
boolean mayor= (b > a); //la variable mayor quedará con el valor *false*, pues el valor de b es menor que el valor de a.

boolean menorIgual = (b <= c); //La variable menor igual quedará con el valor de *true*, pues el valor de b es menor que el valor de c.
```

sirven para hacer hacer comparaciones y retornan un valor booleano

## operadores logicos

- `&&` and o conyuncion
- `||` or o disyuncion
- `!` not o negacion

tambien sirven para hacer comparaciones y devuelven un valor booleano pero estos siguen los criterios de las tablas de verdad 

```java
boolean a = true;
boolean b = false;

//====AND====

if (a && b) {
   // Este código no será ejecutado, ya que a es verdadero y b es falso
}

//====OR====

if (a || b) {
   //Este código será ejecutado, ya que a es verdadero aunque b sea falso 
}

//====NOT====

if (!a) {
   // Este código no será ejecutado, ya que a es verdadero
}
```

---
# convenciones 

### nombre de clases
se utiliza **Upper CamelCase**, es decir que empieza con mayuscula y cada palabra tabien, todo sin espacio

```java
public class MiClase {}
```

### nombre de un metodo
Los nombres de los métodos deben comenzar con una letra minúscula y seguir la convención camelCase.

```java
public static void mostrarMensaje() {
    System.out.println("¡Hola desde el método!");
}
```

### nombre de las constantes
los nombres de las constantes deben estar completamente en mayusculas y las palabras separadas por un guion

```java
final double PI = 3.14159;
final int VELOCIDAD_LUZ = 299792458;
final String NOMBRE_APLICACION = "Mi Aplicación";
final boolean ES_ACTIVO = true;
final char INICIAL = 'J';
```

### nombre de una variable
Los nombres de las variables deben comenzar con una letra minúscula y seguir la convención camelCase. Al igual que los metodos

```java
int cantidad = 10;
double precio = 99.99;
char letra;
boolean esValido,bandera,;
String mensaje = "¡Hola!", mensaje1 = "";

```

##### ==dato de color:
>las variabales se pueden declarar de distintas maneras sin importar el tipo de variable que sea
>>- con inicializacion ej linea 1 y 2
>>- sin inicializacion ej linea 3
>>- multiple variable de un tipo sin inicializacion ej linea 4
>>- multiple variable de un tipo con inicializacion ej linea 5==

---
## tipo de variable


- ### **boolean:**
El tipo boolean se utiliza para representar valores lógicos y puede tener solo dos valores: true o false. Se utiliza en expresiones condicionales, bucles y otros casos en los que se desea evaluar si una determinada condición es verdadera o falsa.

- ### **byte:**
El tipo byte se utiliza para representar valores numéricos enteros de 8 bits. Tiene un rango de valores de -128 a 127.

- ### **char:**
El tipo char se utiliza para representar caracteres individuales. Puede almacenar cualquier carácter Unicode y se representa con comillas simples ('').

- ### **short:**
El tipo short se utiliza para representar valores numéricos enteros de 16 bits. Tiene un rango de valores de -32.768 a 32.767.

- ### **int:**
El tipo int se utiliza para representar valores numéricos enteros de 32 bits. Es uno de los tipos de datos más utilizados para representar números enteros en Java y tiene un rango de valores de -2.147.483.648 a 2.147.483.647.

- ### **long:**
El tipo long se utiliza para representar valores numéricos enteros de 64 bits. Se utiliza para representar valores enteros muy grandes y tiene un rango de valores de -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807.

- ### **float:**
El tipo float se utiliza para representar valores numéricos de punto flotante, es decir, valores con decimales. Ocupa 32 bits de memoria. Puede representar números decimales con hasta siete dígitos y tiene una precisión limitada, lo que significa que puede redondear los números si son demasiado grandes o demasiado pequeños.

- ### **double:**
El tipo double es similar al float, pero ocupa 64 bits de memoria y puede representar números decimales con hasta quince dígitos.