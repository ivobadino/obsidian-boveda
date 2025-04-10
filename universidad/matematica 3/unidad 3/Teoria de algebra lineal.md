---
tags:
  - mate3
---
# [[Álgebra Lineal]]

---

Aunque algunos pueden confundir el **álgebra lineal** con el **álgebra básica**, en realidad es mucho más abstracta, centrada en `vectores` y `matrices`.

Se ocupa de sistemas lineales representados a través de espacios vectoriales y matrices.

Si no estás familiarizado con estos conceptos, no hay problema; los vamos a explorar detalladamente.

El álgebra lineal es fundamental en varias áreas aplicadas como estadísticas, investigación operativa, ciencia de datos y aprendizaje automático.

Cuando trabajas con datos en estas áreas, estás utilizando álgebra lineal, muchas veces sin darte cuenta.

Es posible evitar el aprendizaje profundo del álgebra lineal por un tiempo, gracias a las bibliotecas de aprendizaje automático y estadísticas que automatizan estos procesos. Sin embargo, para realmente comprender lo que sucede detrás de las escenas y trabajar de manera más efectiva con los datos, es inevitable entender los fundamentos del álgebra lineal.

Aunque es un tema extenso que no podemos abarcar completamente en una sola clase, podemos aprender lo suficiente para sentirnos más cómodos con él y movernos de manera efectiva en el ámbito de la ciencia de datos. Además, habrá oportunidades de aplicar estos conceptos en capítulos posteriores.

---

keyboard_arrow_down

### ¿Qué es un vector?

---

Según los físicos, un vector es una flecha en el espacio con una dirección y longitud específicas, que suele representar datos, por ejemplo, velocidad y dirección.

Para un programador, un vector es una lista ordenadas de números que se pueden sumar entre sí, y la dimensión del vector es qué cantidad de elementos tiene esa lista.

Para un matemático, un vector es un conjunto de cosas que se pueden **sumar entre ellos y multiplicar por un número**.

En criollo, es una flecha que tiene principio, fin, dirección, largo y sentido.

Es el pilar central del álgebra lineal, incluyendo matrices y transformaciones lineales.

En su forma más fundamental, no tiene un concepto de ubicación, así que siempre imagina que su cola comienza en el origen de un plano cartesiano (0,0).

La figura que sigue muestra un vector que avanza tres pasos en dirección horizontal y dos pasos en la vertical.

---

El propósito del vector es representar visualmente un pedazo de datos.

Si tenemos un registro de datos para los metros cuadrados de una casa de 1.672 metros cuadrados y su valoración de $260.000, podríamos expresar eso como un vector [1672, 260000], avanzando 1.672 pasos en dirección horizontal y 260.000 pasos en la dirección vertical.

Declaramos un vector matemáticamente así:

v→=[xy]

Poniendo valores:

v→=[32]

Podemos declarar un vector usando una colección simple de Python, como una lista común y corriente, o como vimos en la clase anterior: utilizando `numpy`.

---

**Nota:** Cuando comenzamos a realizar cálculos matemáticos con vectores, especialmente al realizar tareas como el aprendizaje automático, probablemente deberíamos usar la biblioteca `NumPy`, ya que es más eficiente que las listas de Python nativas.

---

	v = [3, 2]  
	print(v)  
	
	[3, 2]

---


	import numpy as np  
	v = np.array([3, 2])  
	print(v)  
	print(v.shape)  
	
	[3 2]
	(2,)

---

**Importante:** Python es lento en términos computacionales, ya que no se compila a código de máquina de bajo nivel o bytecode como Java, C#, C, etc. Se interpreta de manera dinámica en tiempo de ejecución. Sin embargo, las bibliotecas numéricas y científicas de Python no son lentas.

Bibliotecas como NumPy están escritas en lenguajes de bajo nivel como C y C++, por eso son computacionalmente eficientes.

Python realmente actúa como un "código pegamento" integrando estas bibliotecas para tus tareas.

---

keyboard_arrow_down

## Dimensiones

El vector "v" que declaramos recién, es de 2 dimensiones, y es difícil imaginarse un vector de más de 3 dimensiones. Pero en realidad, nos alcanza con saber que podemos generalizar y podemos tener vectores de tantas dimensiones como queramos:

v→=⎛⎝⎜⎜⎜⎜⎜⎜321829⎞⎠⎟⎟⎟⎟⎟⎟

---

[ ]

v = np.array([3, 2, 18, 2, 9])  
print(v)  
print(v.shape)  

[ 3  2 18  2  9]
(5,)

---

keyboard_arrow_down

## Sumar Vectores

Efectivamente combinamos los movimientos de dos vectores en un solo vector.

Digamos que tenemos dos vectores:

v→;w→

¿Cómo los sumamos?

---

Numéricamente es bastante sencillo: sumamos los valores del eje _x_ y eso nos va a dar la resultante en _x_, y hacemos lo mismo para el eje _y_.

v→+w→=(32)+(2−1)

v→+w→=(3+22+(−1))

v→+w→=(51)

---

[ ]

from numpy import array  
  
v = array([3,2])  
w = array([2,-1])  
  
# sum the vectors  
v_plus_w = v + w  
  
# display summed vector  
print(v_plus_w)  

[5 1]

---

Visualmente, esto es como correr la base del vector a sumar donde termina el vector anterior:  

---

Y veamos que es lo mismo cuál de los dos sumo primero, es decir, la adición de vectores es conmutativa:  

---

keyboard_arrow_down

## Escalando Vectores

Escalar es aumentar o disminuir la longitud de un vector. Se puede hace crecer/reducir un vector multiplicándolo o escalándolo con un valor único, conocido como escalar.

Matemáticamente, esto es multiplicar cada una de las dimensiones por el escalar.

v→=(31)

2v→=2(31)=(2×32×1)=(62)

---

[ ]

v = array([3,1])  
  
# scale the vector  
scaled_v = 2.0 * v  
  
# display scaled vector  
print(scaled_v)  

[6. 2.]

---

keyboard_arrow_down

#### Manipular datos es manipular vectores

Cada operación con datos puede pensarse en términos de vectores, incluso promedios simples.

Tomemos el escalado, por ejemplo.

Digamos que intentábamos obtener el valor promedio de una casa y el metraje cuadrado promedio para todo un vecindario.

Sumaríamos los vectores juntos para combinar su valor y metraje cuadrado respectivamente, dándonos un vector gigante que contiene tanto el valor total como el metraje cuadrado total.

Luego, escalamos hacia abajo el vector dividiéndolo por el número de casas _N_, que realmente es multiplicar por _1/N_. Ahora tenemos un vector que contiene el valor promedio de la casa y el metraje cuadrado promedio.

---

**Nota:** Escalar un vector no le cambia la dirección, solamente lo estira o lo contrae. Lo importante de notar es que si el escalar es negativo, no cambia la dirección pero sí el sentido.

---

---

keyboard_arrow_down

#### Extensión y Dependencia Lineal

Estas dos operaciones, sumar dos vectores y escalarlos, dan lugar a una idea simple pero poderosa:

- Con estas dos operaciones, podemos combinar dos vectores y escalarlos para crear cualquier vector resultante que queramos.

En la imagen vemos 6 ejemplos de tomar dos vectores, escalarlos y sumarlos.

Estos vectores:

v→;w→

Tienen cada uno su dirección y sentido fijos, pero pueden ser escalados y combinados para crear **cualquier** otro vector nuevo.

---

De nuevo, estos vectores tienen direcciones fijas, excepto por el cambio con escalares negativos, pero podemos usar el escalado para crear libremente cualquier vector compuesto por estos dos originales.

Todo este espacio de vectores posibles se llama extensión, y en la mayoría de los casos nuestra extensión puede crear vectores ilimitados a partir de esos dos vectores, simplemente escalándolos y sumándolos.

**Pregunta:** ¿en qué caso estamos limitados en los vectores que podemos crear?

---

Cuando tenemos dos vectores en dos direcciones diferentes, son linealmente independientes y tienen esta extensión ilimitada.

¿Qué pasa cuando dos vectores existen en la misma dirección o existen en la misma línea?

La combinación de esos vectores también está limitada a la misma línea, limitando nuestra extensión a solo esa línea. No importa cómo lo escales, el vector suma resultante también está limitado a esa misma línea. Esto los hace **linealmente dependientes**.

---

¿Y cómo podría encontrarme con este mismo problema en más dimensiones?

Por ejemplo, si tengo 3 o más dimensiones, capaz que son linealmente dependientes entre sí y quedo limitado.

**Nota:** Más adelante vamos a revisar el concepto de determinante que nos ayuda con este problema.

---

¿Pero por qué nos importa si dos vectores son linealmente dependientes o independientes?

Muchos problemas se vuelven difíciles o irresolubles cuando son linealmente dependientes. Por ejemplo, cuando aprendamos sobre sistemas de ecuaciones más adelante en este capítulo, un conjunto de ecuaciones linealmente dependiente puede hacer que las variables desaparezcan y volver el problema irresoluble.

¡Pero si tenemos independencia lineal, esa flexibilidad para crear cualquier vector que necesites a partir de dos o más vectores se vuelve invaluable para encontrar una solución!

---

keyboard_arrow_down

## Transformaciones lineales

---

Este concepto de sumar dos vectores con dirección fija, pero escalarlos para tener distintos resultados de las sumas, es bastante importante.

Este vector resultante, exceptuando los casos de dependencia lineal, nos puede apuntar en cualquier dirección, y puede tener el largo que nosotros queramos.

Esto prepara la intuición para transformaciones lineales, donde usamos vectores para llegar a otros, de un estilo de "funciones".

---

keyboard_arrow_down

### Vectores Base

---

Los vectores conocidos como vectores base, se utilizan para describir transformaciones en otros vectores. Típicamente tienen una longitud de 1 y apuntan en direcciones positivas perpendiculares.

Piensa en los vectores base como bloques de construcción para construir o transformar cualquier vector.

---

Nuestro vector base se expresa en una matriz de 2x2, donde la primera columna es _i_ y la segunda _j_

i→=(10)

j→=(01)

base=(1001)

---

Una matriz es una colección de vectores (como _î_ y _^j_) que puede tener múltiples filas y columnas, y es una forma conveniente de empaquetar datos. Podemos usar _i_ y _j_ para crear cualquier vector que deseemos escalándolos y sumándolos.

Comencemos con el vector

v→=(11)

¿Cómo logramos que el vector _v_ apunte al [3, 2]? Veamos qué sucede si multiplicamos a _î_ por un factor de 3 y a _j_ por un factor de 2 y luego los sumamos

3i→=3(10)=(30)

2j→=2(01)=(02)

v→=(30)+(02)=(32)

---

Esto se conoce como una **transformación lineal**, donde modificamos un vector mediante estiramiento, compresión, inclinación o rotación, siguiendo los movimientos de los vectores base. En resumen, al escalar los vectores _î_ y _j_, también estiramos el espacio en el que se encuentra el vector _v_

---

Generalmente, en transformaciones lineales hay cuatro movimientos que se pueden hacer: escalar, rotar, inclinar

---

Estas cuatro transformaciones lineales son una parte central del álgebra lineal. Escalar un vector lo estirará o lo comprimirá. Las rotaciones girarán el espacio vectorial, y las inversiones darán la vuelta al espacio vectorial para que _î_ y _j_ intercambien sus lugares respectivos.

---

**Importante:** no puedes tener transformaciones que sean no lineales, lo que resultaría en transformaciones curvas o sinuosas que ya no respetan una línea recta. ¡Por eso lo llamamos álgebra lineal, no álgebra no lineal!

---

keyboard_arrow_down

### Multiplicación de matrix por vector

[ ]

subdirectory_arrow_right10 celdas ocultas

---

keyboard_arrow_down

## Multiplicación de matrices

---

La multiplicación de matrices se puede entender como la aplicación de múltiples transformaciones sucesivas a un espacio vectorial. Cada matriz representa una transformación, y al multiplicar las matrices, combinamos estas transformaciones en una sola operación. Es como aplicar una serie de funciones a un vector, donde cada función representa una etapa de transformación.

---

Así aplicamos una rotación y luego un shear o sesgo/corte a un vector [x, y]

(1011)(01−10)(xy)

---

En realidad, podemos consolidar estas dos transformaciones utilizando esta fórmula, aplicando una transformación sobre la última.

(acbd)(egfh)=(ae+bgce+dyaf+bhcf+dh)

---

Para ejecutar esto en Python usando NumPy, puedes combinar las dos matrices simplemente usando el operador matmul() o @

---

[ ]

from numpy import array  
  
# Transformacion 1  
i_hat1 = array([0, 1])  
j_hat1 = array([-1, 0])  
transform1 = array([i_hat1, j_hat1]).transpose()  
  
# Transformacion 2  
i_hat2 = array([1, 0])  
j_hat2 = array([1, 1])  
transform2 = array([i_hat2, j_hat2]).transpose()  
  
# Combino Transformaciones  
combined = transform2 @ transform1  
  
# Test  
print("COMBINED MATRIX:\n {}".format(combined))  
  
# Aplico al vector v  
v = array([1, 2])  
print(combined.dot(v))  

COMBINED MATRIX:
 [[ 1 -1]
 [ 1  0]]
[-1  1]

---

**Importante:** ¡El orden en el que se aplica cada transformación importa! Los productos punto de matrices no son conmutativos.

Piensa en cada transformación como una función, y las aplicamos de la más interna a la más externa, al igual que las llamadas de funciones anidadas.

---

Veamos el ejemplo anterior pero aplicando las transformaciones en otro orden:

---

[ ]

from numpy import array  
  
# Transformacion 1  
i_hat1 = array([0, 1])  
j_hat1 = array([-1, 0])  
transform1 = array([i_hat1, j_hat1]).transpose()  
  
# Transformacion 2  
i_hat2 = array([1, 0])  
j_hat2 = array([1, 1])  
transform2 = array([i_hat2, j_hat2]).transpose()  
  
# Combino transformaciones, en otro orden  
combined = transform1 @ transform2  
  
# Test  
print("COMBINED MATRIX:\n {}".format(combined))  
  
# Aplico al vector v  
v = array([1, 2])  
print(combined.dot(v))  

COMBINED MATRIX:
 [[ 0 -1]
 [ 1  1]]
[-2  3]

---

**Las transformaciones lineales y matrices son fundamentales en la ciencia de datos y el aprendizaje automático. Aunque rara vez visualizamos nuestros datos como espacios vectoriales y transformaciones lineales debido a la alta dimensionalidad, comprender la interpretación geométrica nos ayuda a entender el propósito y el efecto de las operaciones numéricas que realizamos. Esto nos permite aplicar conceptos de álgebra lineal de manera más efectiva en problemas de datos y aprendizaje automático.**

---

keyboard_arrow_down

## Determinantes

---

Cuando realizamos transformaciones lineales, a veces "expandimos" o "comprimimos" el espacio y el grado en que esto sucede puede ser útil.

---

El determinante describe cuánto cambia el tamaño de un área muestreada en un espacio vectorial debido a las transformaciones lineales. Es una medida de cuánto se "expande" o "comprime" el área bajo la transformación y proporciona información útil sobre el efecto global de la transformación en el espacio vectorial.

En la figura, el área aumenta 6 veces.

---

Calculemos el determinante en Python:

---

[ ]

from numpy.linalg import det  
from numpy import array  
  
i_hat = array([3, 0])  
j_hat = array([0, 2])  
  
basis = array([i_hat, j_hat]).transpose()  
  
determinant = det(basis)  
  
print(determinant)  

6.0

---

Las deformaciones simples y las rotaciones no deberían afectar al determinante, ya que el área no cambia. En la siguiente figura se observa que un corte simple no cambia el área.

---

Lo podemos comprobar numéricamente

---

[ ]

from numpy.linalg import det  
from numpy import array  
  
i_hat = array([1, 0])  
j_hat = array([1, 1]) # Transformacion solo en vector j  
  
basis = array([i_hat, j_hat]).transpose()  
  
determinant = det(basis)  
  
print(determinant)  

1.0

---

Cuando escalamos una transformación, el determinante puede aumentar o disminuir, ya que esto afectará el área muestreada en el espacio vectorial. Si la orientación se invierte, es decir, si los vectores base intercambian posiciones en el sentido de las agujas del reloj, el determinante será negativo.

---

[ ]

# Un determinante negativo  
from numpy.linalg import det  
from numpy import array  
  
i_hat = array([-2, 1])  
j_hat = array([1, 2])  
  
basis = array([i_hat, j_hat]).transpose()  
  
determinant = det(basis)  
  
print(determinant)  

-5.000000000000001

---

Debido a que este determinante es negativo, rápidamente observamos que la orientación ha cambiado. Pero, de lejos, la información más crítica que te proporciona el determinante es si la transformación es linealmente dependiente. Si tienes un determinante igual a 0, eso significa que todo el espacio ha sido comprimido en una dimensión menor.

En la siguiente figura vemos dos transformaciones linealmente dependientes, donde un espacio 2D se comprime en una dimensión y un espacio 3D se comprime en dos dimensiones. El área y el volumen respectivamente en ambos casos son 0.

---

Comprobar si el determinante es igual a 0 es muy útil para detectar si una transformación tiene dependencia lineal. Cuando encuentres esto, es probable que te enfrentes a un problema difícil o incluso insoluble.

---

keyboard_arrow_down

## Tipos de matrices especiales

---

### Matriz cuadrada

La matriz cuadrada es una matriz que tiene el mismo número de filas y columnas:

⎛⎝⎜454210791⎞⎠⎟

Principalmente se utilizan para representar transformaciones lineales y son un requisito para muchas operaciones como la descomposición en auto valores.

---

### Matriz identidad

La matriz identidad es una matriz cuadrada que tiene una diagonal de 1 mientras que los otros valores son 0:

⎛⎝⎜100010001⎞⎠⎟

La matriz identidad es especial porque representa la ausencia de cualquier transformación. Cuando la utilizamos en operaciones matriciales, actúa como el "estado inicial" o la base original antes de cualquier transformación. Esto es útil para deshacer transformaciones y resolver sistemas de ecuaciones.

---

### Matriz inversa

Una matriz inversa es aquella que revierte la transformación realizada por otra matriz.

Supongamos la matriz A:

A=⎛⎝⎜459233476⎞⎠⎟

La inversa de la matriz es:

A−1=⎛⎝⎜−1/211/2−20−211/34/31/3⎞⎠⎟

Cuando realizamos la multiplicación de matrices entre la inversa y A obtenemos una matriz identidad.

A−1A=⎛⎝⎜−1/211/2−20−211/34/31/3⎞⎠⎟⎛⎝⎜459233476⎞⎠⎟=⎛⎝⎜100010001⎞⎠⎟

---

### Matriz diagonal

Similar a la matriz identidad está la matriz diagonal, que tiene una diagonal de valores no nulos mientras que el resto de los valores son 0. Las matrices diagonales son deseables en ciertos cálculos porque representan escalares simples aplicados a un espacio vectorial. Aparecen en algunas operaciones de álgebra lineal.

⎛⎝⎜400020005⎞⎠⎟

---

### Matriz triangular

Similar a la matriz diagonal está la matriz triangular, que tiene una diagonal de valores no nulos frente a un triángulo de valores, mientras que el resto de los valores son 0.

⎛⎝⎜400210965⎞⎠⎟

Las matrices triangulares son deseables en muchas tareas de análisis numérico, ya que suelen ser más fáciles de resolver en sistemas de ecuaciones.

---

### Matriz dispersa

Las matrices dispersas son aquellas en las que la mayoría de los elementos son cero. Desde el punto de vista computacional, son útiles porque no necesitan almacenar los ceros, lo que ahorra espacio de memoria y acelera los cálculos en operaciones matriciales.

⎛⎝⎜⎜⎜000000000200⎞⎠⎟⎟⎟

Cuando tienes matrices grandes y dispersas, es posible que uses explícitamente una función de dispersión para crear tu matriz.

---

keyboard_arrow_down

## Sistemas de ecuaciones y la matriz inversa

Uno de los casos de uso básicos para álgebra lineal es resolver sistemas de ecuaciones.

Los sistemas de ecuaciones también sirven para aprender sobre matrices inversas.

Supongamos que tenemos las siguientes ecuaciones y tenés que resolverlas para _x_, _y_ y _z_:

4x+2y+4z=44

5x+3y+7z=56

9x+3y+6z=72

---

Podemos probar a mano despejar las ecuaciones, y llegaríamos al resultado, pero si queremos dárselo a una compu para que lo resuelva, podríamos expresar este problema en notación matricial.

Veamos cómo quedaría:

A=⎛⎝⎜459233476⎞⎠⎟

B=⎛⎝⎜445672⎞⎠⎟

X=⎛⎝⎜xyz⎞⎠⎟

---

Quedando el sistema de ecuaciones lineales:

AX=B

O sea:  

⎛⎝⎜459233476⎞⎠⎟.⎛⎝⎜xyz⎞⎠⎟=⎛⎝⎜445672⎞⎠⎟

---

Y si es que este sistema de ecuaciones tiene solución, nosotros podríamos despejar _X_ y obtener qué set de valores _x_, _y_ y _z_ satisfacen la igualdad.

¿Cómo se despeja esto teniendo matrices?

---

---

AX=B

  

A−1AX=A−1B

  

X=A−1B

Ahora tenemos que calcular la inversa de la matriz _A_, que como acá nos importa el concepto y no las cuentas (porque las vamos a hacer con _numpy_), quedaría:

A−1=⎛⎝⎜−1/211/2−20−211/34/31/3⎞⎠⎟

---

Pero siempre podemos corroborar que si la multiplicamos por _A_, vamos a obtener la matriz identidad:

A−1A=⎛⎝⎜−1/211/2−20−211/34/31/3⎞⎠⎟⎛⎝⎜459233476⎞⎠⎟=⎛⎝⎜100010001⎞⎠⎟

---

Como _numpy_ aproxima y no hace las cuentas exactas, para mostrar el ejemplo con _Python_ y que nos dé exactamente la matriz identidad, vamos a usar el paquete _sympy_.

---

[ ]

from sympy import *  
  
# 4x + 2y + 4z = 44  
# 5x + 3y + 7z = 56  
# 9x + 3y + 6z = 72  
  
A = Matrix([  
    [4, 2, 4],  
    [5, 3, 7],  
    [9, 3, 6]  
])  
  
# El producto entre A y su inversa  
# producen la matriz identidad  
inverse = A.inv()  
identity = inverse * A  # Ojo que esto no es numpy, es sympy, acá las matrices se multiplican con *  
  
print("INVERSE: {}".format(inverse))  
print("IDENTITY: {}".format(identity))  

INVERSE: Matrix([[-1/2, 0, 1/3], [11/2, -2, -4/3], [-2, 1, 1/3]])
IDENTITY: Matrix([[1, 0, 0], [0, 1, 0], [0, 0, 1]])

---

Pero bueno, las aproximaciones de _numpy_ no nos van a empeorar mucho las cuentas, y la realidad es que es la forma de hacerlo.

La resolución del sistema de ecuaciones quedaría así:

---

[ ]

from numpy import array  
from numpy.linalg import inv  
  
# 4x + 2y + 4z = 44  
# 5x + 3y + 7z = 56  
# 9x + 3y + 6z = 72  
  
A = array([  
    [4, 2, 4],  
    [5, 3, 7],  
    [9, 3, 6]  
])  
  
B = array([  
    44,  
    56,  
    72  
])  
  
# Inversa de A por A debería darnos la matrix identidad:  
print(inv(A) @ A)  
  

[[ 1.00000000e+00 -2.22044605e-16 -4.44089210e-16]
 [ 2.66453526e-15  1.00000000e+00  1.77635684e-15]
 [-6.66133815e-16 -2.22044605e-16  1.00000000e+00]]

---

[ ]

# La resolución del sistema de ecuaciones:  
  
X = inv(A).dot(B)  
  
print('X =', X)  

X = [ 2. 34. -8.]

---

Esto significa que:  

A−1B=X

  

⎛⎝⎜−1/211/2−20−211/34/31/3⎞⎠⎟.⎛⎝⎜445672⎞⎠⎟=⎛⎝⎜xyz⎞⎠⎟

  

⎛⎝⎜234−8⎞⎠⎟=⎛⎝⎜xyz⎞⎠⎟

---

keyboard_arrow_down

## Autovectores y autovalores

---

La _descomposición de matrices_ consiste en descomponer una matriz en sus componentes básicos, de manera similar a como se factorizan los números (por ejemplo, 10 se puede descomponer en 2 × 5).

La descomposición de matrices es útil para tareas como encontrar matrices inversas y calcular determinantes, así como para la regresión lineal. Hay varios métodos de descomposición de matrices.

---

En este capítulo nos enfocaremos en un método común conocido como descomposición en autovalores, que se utiliza frecuentemente en el aprendizaje automático y el análisis de componentes principales. A este nivel, no profundizaremos en cada una de estas aplicaciones. Básicamente, la descomposición en autovalores nos ayuda a descomponer una matriz en partes más simples que son más útiles para diferentes tareas de aprendizaje automático. Es importante tener en cuenta que este método solo funciona con matrices cuadradas.

---

---

Si tenemos una matriz cuadrada A, tiene la siguiente ecuación de autovalores:

Aν=λν

---

Veamos cómo se calculan los autovalores (eigenvalues) y autovectores (eigenvectors) en Python:

---

[ ]

from numpy import array, diag  
from numpy.linalg import eig, inv  
  
A = array([  
    [1, 2],  
    [4, 5]  
])  
  
eigenvals, eigenvecs = eig(A)  
  
print("EIGENVALUES")  
print(eigenvals)  
print("\nEIGENVECTORS")  
print(eigenvecs)  

EIGENVALUES
[-0.46410162  6.46410162]

EIGENVECTORS
[[-0.80689822 -0.34372377]
 [ 0.59069049 -0.9390708 ]]

---

Entonces, ¿cómo reconstruimos la matriz A a partir de los autovectores y autovalores?

Recuerda la fórmula:

Aν=λν

Para encontrar A debemos realizar

A=QΛQ−1

Donde Q representa a los autovectores, Λ son los autovalores en forma diagonal y luego tenemos la matriz inversa de Q.

---

Veamos el siguiente ejemplo en Python, comenzando por descomponer la matriz y luego recomponerla.

---

[ ]

from numpy import array, diag  
from numpy.linalg import eig, inv  
  
A = array([  
    [1, 2],  
    [4, 5]  
])  
  
# Descompongo la matriz A  
eigenvals, eigenvecs = eig(A)  
  
print("EIGENVALUES")  
print(eigenvals)  
print("\nEIGENVECTORS")  
print(eigenvecs)  
  
# Recompongo la matriz A  
print("\nREBUILD MATRIX")  
Q = eigenvecs  
R = inv(Q)  
  
L = diag(eigenvals)  
B = Q @ L @ R  
  
print(B)  

EIGENVALUES
[-0.46410162  6.46410162]

EIGENVECTORS
[[-0.80689822 -0.34372377]
 [ 0.59069049 -0.9390708 ]]

REBUILD MATRIX
[[1. 2.]
 [4. 5.]]

---

keyboard_arrow_down

## Ejercicios

---

arrow_upward

arrow_downward

link

comment

edit

delete

more_vert

1. Relizar la transformación lineal de _v_ = [1, 2] si _î_ = [2, 0] y _j_ = [0, 3/2]
2. Relizar la transformación lineal de _v_ = [1, 2] si _î_ = [-2, 1] y _j_ = [1, -2]
3. Cuál es el determinante de la transformación si _î_ = [1, 0] y _j_ = [2, 2]
4. ¿Se pueden realizar dos o más transformaciones lineales en una sola transformación lineal? ¿Por qué sí o por qué no?
5. Resolver el siguiente sistema de ecuaciones
    
    3x+y+0z=54
    
    2x+4y+z=12
    
    3x+y+8z=6
    
6. ¿La siguiente matriz es linealmente dependiente? ¿Por qué sí o por qué no?
    
    (2613)