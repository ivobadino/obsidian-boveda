---
tags:
  - mate3
---
![[MATE 3#Unidad 3 Álgebra Lineal]]

[[Teoria de algebra lineal]]

El álgebra lineal es una rama de las matemáticas que se centra en el estudio de vectores, matrices, sistemas de ecuaciones lineales y transformaciones lineales. Es fundamental en muchas áreas de la ciencia y la ingeniería, incluyendo la programación.

**¿Cómo se implementa el álgebra lineal en la programación?**

El álgebra lineal se utiliza en programación para resolver una amplia variedad de problemas, especialmente aquellos que involucran grandes cantidades de datos o cálculos complejos. Algunas de las aplicaciones más comunes incluyen:

- **Gráficos por computadora:**
    - El álgebra lineal es esencial para la manipulación de gráficos 2D y 3D. Se utiliza para realizar transformaciones como rotación, traslación y escalado de objetos.
    - Las matrices se utilizan para representar objetos 3D y las operaciones matriciales se utilizan para realizar transformaciones en esos objetos.
- **Procesamiento de imágenes y video:**
    - Las imágenes y los videos se pueden representar como matrices de píxeles. El álgebra lineal se utiliza para realizar operaciones como el filtrado, la compresión y la detección de bordes.
    - Las transformaciones lineales se utilizan para cambiar el tamaño, la orientación y la perspectiva de las imágenes y los videos.
- **Aprendizaje automático (Machine Learning):**
    - El álgebra lineal es la base de muchos algoritmos de aprendizaje automático. Se utiliza para representar datos, realizar cálculos y optimizar modelos.
    - Las matrices y los vectores se utilizan para representar conjuntos de datos y las operaciones matriciales se utilizan para realizar cálculos en esos datos.
- **Inteligencia artificial:**
    - El algebra lineal es la base para el Deep Learning, con la creación y manipulación de tensores, que son matrices multidimensionales.
    - Se utiliza para desarrollar redes neuronales, que son modelos matemáticos que pueden aprender de los datos.
- **Simulación y modelado:**
    - El álgebra lineal se utiliza para simular y modelar sistemas físicos y biológicos. Por ejemplo, se puede utilizar para modelar el flujo de fluidos, la propagación de ondas y la dinámica de poblaciones.
    - También es usado en la creación de videojuegos, para la creación de las físicas dentro del juego.

En resumen, el álgebra lineal es una herramienta poderosa que se utiliza en muchas áreas de la programación. Su capacidad para manipular grandes cantidades de datos y realizar cálculos complejos la hace esencial para resolver una amplia variedad de problemas.

# vectores

para nosotros los vectores son listas ordenadas de numeros que se pueden sumar entre si, y la dimensión de ese vector es la cantidad de elementos que tiene esa lista.

es el pilar central del algebra lineal, incluyendo matrices y transformaciones lineales

Declaramos un vector matemáticamente así:

  

$$\overrightarrow{v}={x\brack y}$$

  

Poniendo valores:

  

$$\overrightarrow{v}={3\brack 2}$$

  
  

Podemos declarar un vector usando una colección simple de Python, como una lista común y corriente, o como vimos en la clase anterior: utilizando `numpy`.

- con librerias de python:

		v = [3, 2]
		print(v)

esto devuelve: 
[3, 2]

- con la libreria de `numpy`

		import numpy as np
		v = np.array([3, 2])
		print(v)
		print(v.shape)
esto devuelve :
[3 2]
(2, )

# dimensiones


un vector puede tener las dimenciones que se quiera, talvez es dificil concebir la idea de algo de mas de tres dimenciones ,  por el echo de que no nos podemos imaginar nada mas alla de las tres dimenciones que componen nuestro entorno.

en python:

	v = np.array([3, 2, 18, 2, 9])
	print(v)
	print(v.shape)

esto nos dara dos resultados:
[ 3 2 18 2 9] 
(5,)

# suma de vectores

lo que hace la suma de vectores es combinar las magnitudes y direcciones de dos o mas vectores , dandonos como resultado un vector resultante con la combinacion de los vectores involucrados

#### **En términos más sencillos:**

- Imagina que cada vector es una flecha que representa un movimiento.
- La suma de vectores es como seguir esos movimientos uno tras otro.
- El vector resultante es la flecha que va desde el punto de inicio del primer movimiento hasta el punto final del último movimiento.

## como se suma??

Numéricamente es bastante sencillo: sumamos los valores del eje *x* y eso nos va a dar la resultante en *x*, y hacemos lo mismo para el eje *y*.

  

$$\overrightarrow{v} + \overrightarrow{w} = \left(\begin{matrix} 3 \\ 2 \end{matrix}\right) + \left(\begin{matrix} 2 \\ -1 \end{matrix}\right)$$

  

$$\overrightarrow{v} + \overrightarrow{w} = \left(\begin{matrix} 3 + 2 \\ 2 + (-1) \end{matrix}\right) $$

  

$$\overrightarrow{v} + \overrightarrow{w} = \left(\begin{matrix} 5 \\ 1 \end{matrix}\right) $$

en python:

	from numpy import array
	v = array([3,2])
	w = array([2,-1])
	v_plus_w = v + w
	print(v_plus_w)

los que nos da como resultado el vector: [5 1]

# escalar vectores

no es mas que multiplicar un vector por un numero escalar

$$\overrightarrow{v} = \left(\begin{matrix} 3 \\ 1 \end{matrix}\right) $$

$$ 2 \overrightarrow{v} = 2 \left(\begin{matrix} 3 \\ 1 \end{matrix}\right) = \left(\begin{matrix} 2 \times 3 \\  2 \times 1 \end{matrix}\right) = \left(\begin{matrix} 6 \\  2 \end{matrix}\right) $$
esto nos da como resultado un vector el cual cada componente de este sera multiplicada por el escalar

en python:

	v = array([3,1])
	scaled_v = 2.0 * v
	print(scaled_v)

los que nos da como resultado el vector escalado: [6 2]

# extension y dependencia lineal


## **Extensión Lineal (Span):**

- Es el conjunto de todas las posibles combinaciones lineales de un conjunto de vectores. En otras palabras, es el espacio vectorial que "abarcan" esos vectores.

- Imagina que tienes un conjunto de "flechas" (vectores). La extensión lineal es como un "lienzo" que puedes pintar con todas las posibles combinaciones de esas flechas.

- Si tienes dos flechas que apuntan en direcciones diferentes, puedes pintar todo el plano. Si tienes tres flechas que no están en el mismo plano, puedes pintar todo el espacio 3D.

- La extensión lineal te dice qué tan grande es el "espacio" que puedes crear con tus vectores.

## dependencia lineal:

- Los vectores son linealmente dependientes si uno de ellos es "redundante". Esto significa que puedes dibujar uno de los vectores usando los otros.

- Si tienes dos flechas que apuntan en la misma dirección, son dependientes. No puedes pintar todo el plano con ellas, solo puedes pintar una línea.

- La dependencia lineal limita el tamaño del "lienzo" que puedes pintar.

# transformaciones lineales

Este concepto de sumar dos vectores con dirección fija, pero escalarlos para tener distintos resultados de las sumas, es bastante importante.

Este vector resultante, exceptuando los casos de dependencia lineal, nos puede apuntar en cualquier dirección, y puede tener el largo que nosotros queramos.

Esto prepara la intuición para transformaciones lineales, donde usamos vectores para llegar a otros, de un estilo de "funciones".

# vectores base

los vectores base se utlilizan para describir transformaciones en otros vectores. tienen tamaño de 1 y apuntan en direcciones positivas perpendiculares

son vectores de los cuales se pueden construir otros vectores


$$\overrightarrow{i} = \dbinom{1}{0} $$
$$\overrightarrow{j} = \dbinom{0}{1} $$
$$ base = \begin{pmatrix}

   1 & 0 \\

   0 & 1

\end{pmatrix} $$


Una matriz es una colección de vectores (como *î* y *^j*) que puede tener múltiples filas y columnas, y es una forma conveniente de empaquetar datos. Podemos usar *i* y *j*  para crear cualquier vector que deseemos escalándolos y sumándolos.

Comencemos con el vector
$$\overrightarrow{v} = \dbinom{1}{1} $$
¿Cómo logramos que el vector *v* apunte al [3, 2]?

Veamos qué sucede si multiplicamos a *î* por un factor de 3 y a *j* por un factor de 2 y luego los sumamos

$$ 3 \overrightarrow{i} = 3 \dbinom{1}{0} = \dbinom{3}{0} $$$$ 2 \overrightarrow{j} = 2 \dbinom{0}{1} = \dbinom{0}{2} $$$$ \overrightarrow{v} = \dbinom{3}{0} + \dbinom{0}{2} = \dbinom{3}{2} $$
Esto se conoce como una **transformación lineal**, donde modificamos un vector mediante estiramiento, compresión, inclinación o rotación, siguiendo los movimientos de los vectores base. En resumen, al escalar los vectores _î_ y _j_, también estiramos el espacio en el que se encuentra el vector _v_

# multiplicacion de una matriz por un vector

La fórmula para transformar un vector *v* dado los vectores base empaquetados como una matriz es la siguiente:

$$ \dbinom{x_{nuevo}}{y_{nuevo}} = \begin{pmatrix} a & b \\ c & d\end{pmatrix} \dbinom{x}{y}$$$$ \dbinom{x_{nuevo}}{y_{nuevo}}  =  \begin{pmatrix} ax + by \\ cx + dy\end{pmatrix}$$
# multiplicacion de matrices


# determinantes

