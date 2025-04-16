---
tags:
  - mate3
---
# datos

los datos por si solos no son relevantes o no del todo, sino aquel significado que le damos.
es decir que si en una memoria tenemos datos binarios, si los observamos asi a simple vista solo veremos una maraña de unos y ceros. El o los usuarios que interactuan o analizan los datos son los que le dan el significado.

Los datos son fotos de la realidad, capturando solo fragmentos de historias completas, y pueden estar **sesgados** o **incompletos**. En la ciencia de datos, apuntamos a recopilar datos enfocados y relevantes para nuestros objetivos, evitando caer en análisis superficiales o conjuntos de datos incompletos. Es crucial cuestionar cómo se crearon los datos y qué no están mostrando.

## sesgos

>En otras palabras, un sesgo introduce un error que hace que los datos recopilados o las conclusiones extraídas de ellos se inclinen de manera no aleatoria hacia una dirección particular, distorsionando la verdadera imagen de lo que se está estudiando. `gemini`
>

los sesgos pueden aparecer por distintos motivos:
- **La forma en que se selecciona la muestra:** Si la muestra no es representativa de la población, las conclusiones que se extraigan de ella pueden no ser válidas para toda la población.
- **La manera en que se miden o recopilan los datos:** Instrumentos de medición defectuosos, preguntas mal formuladas en una encuesta o la influencia del observador pueden introducir sesgos.
- **La forma en que se analizan e interpretan los datos:** Las creencias preexistentes del investigador o la omisión de variables importantes pueden llevar a interpretaciones sesgadas.

![[teoria de estadistica#Ejemplo de sesgado]]

## tipos de sesgos

existen distintas formas de clasificar los sesgos dentro de el campo de la estadistica, segun como influyen en la interpretacion de los datos.

>Sesgo estadístico es un término usado para describir estadísticas que no proporcionan una representación precisa de la población.

- ## sesgo de confirmacion
	el sesgo de confirmacion es aquel que las creencias previas con respecto ciertas tendencias generan una infuencia en el analisis de los datos.
>	**EJEMPLO:** si creemos firmemente que la mayoría de las personas prefieren el helado de vainilla sobre el de chocolate, podríamos prestar más atención a los datos que respaldan esa idea, ignorando información contraria.

- ## sesgo de seleccion 
	el sesgo de seleccion es aquel que susede por tomar muestras de una poblacion que no representa correctamente a todo el grupo objetivo

- ## sesgo de caso atipico 
	el sesgo de caso atipico es aquel que distorciona todo el analisis devido a casos atipicos , por eso es recomendable utilizar la mediana para una representacion mas precisa de la mayoria de la poblacion estudiada.
	> **EJEMPLO: ** al examinar los ingresos en los EEUU, unas pocas personas extremadamente ricas  distrorcionan los calculos de los promedios de ingresos.

- ## sesgo del observador
	el sesgo del observador ocurre devido a la propio subjetividad de este el cual dificilmente posea una plena imparcialidad.**La mejor manera de prevenirlo es aprender a identificarlo**

- ## sesgo de financiacion 
	el sesgo de financiancion es otro caso el cual puede presentar una imparcialidad, debido a que los datos pueden tener tendencia a beneficiar a la entidad que financio los estudios .

- ## sesgo de variable omitida
	el sesgo de la variable omitida  ocurre cuando la ausencia de una variable relevante afecta la validez de los resultados estadísticos.

- ## sesgo del superviviente
	el sesgo del superviviente ocurre cuando solo se consideran los datos de aquellos que sobreviven o tiene exito en una determinada situacion. Al no tener en cuenta todas las fuentes potenciales de datos, se pueden obtener una representacion incompleta o sesgada de la realidad.



# verdad absoluta


# esadistica descriptiva

# promedio y promedio ponderado (*media*)
Hay dos versiones del promedio o media: 

el promedio o media muestral
$$ \bar{x} = \frac{x_{1}+x_{2}+x_{3}+...+x_{n}}{n} = \displaystyle\sum_{}\frac{x_{i}}{n} $$y la media poblacional o simplemente promedio
$$ \mu = \frac{x_{1}+x_{2}+x_{3}+...+x_{n}}{N} = \displaystyle\sum_{}\frac{x_{i}}{N} $$

son la misma cuenta pero depende en que se usen cambia el nombre.

N o n representan el tamano de la muestra y de la poblacion

### promedio ponderado

$$ Promedio Ponderado = \frac{(x_{1} \cdot w_{1}) + (x_{2} \cdot w_{2}) + (x_{2} \cdot w_{2}) + ... + (x_{n} \cdot w_{n})}{w_{1}+w_{2}+w_{3}+...+w_{n}} $$

es un promedio en el cual el que hace es calculo elije que valores tienen mas peso a la hora de hacer el calculo, es decir que podemos ajustar  su contribucion en el promedio final. esto nos permite darle mas importancia a ciertos valores.

hacer el calclulo con estos pesos(weights):

	sample = [90, 80, 63, 87]
	weights = [1.0, 1.0, 1.0, 2.0]
	
	weighted_mean = sum(s * w for s,w in zip(sample, weights)) / sum(weights)
	print(weighted_mean)

da el mismo resultado que hacer :

	sample = [90, 80, 63, 87]
	weights = [.20, .20, .20, .40]
	
	weighted_mean = sum(s * w for s,w in zip(sample, weights)) / sum(weights)
	print(weighted_mean)

esto nos da como resultado en el print : 81.4

es decit que el peso puede ser  1 en un caso y en otro momento puede ser 5, pero si mantentemos la relacion de todos los pesos el resultado del promedio ponderardo no cambiara.

# mediana

es simplemente el valore central de la lista de datos. es decir que si la lista tiene cantidad de datos impares, el valor de esta es el numero que se encuentra en el mitad. y si el tamaño de la lista es par la mediana es el promedio de los dos valores centrales

ejemplo lista impar: lista: [1,2,3,4,5,6,7,8,9]
la mediana es el valor: 5

ejemplo llista par. lista[1,2,3,4,5,6,7,8,9,10]
la mediana es: (5+6)/2= **6.5** 

La mediana puede ser una alternativa útil al promedio cuando los datos están sesgados por valores atípicos, es decir, valores que son extremadamente grandes o pequeños en comparación con el resto de los valores.

>	En 1986, el salario inicial anual promedio de los graduados en geografía de la Universidad de Carolina del Norte en Chapel Hill fue de 250,000.Otrasuniversidadespromediaron22,000. ¿Por qué? Bueno... Michael Jordan fue uno de los graduados de la UNC. Uno de los jugadores de la NBA más famosos de todos los tiempos realmente se graduó con un título en geografía de UNC. Sin embargo, comenzó su carrera jugando al baloncesto, no estudiando mapas. Obviamente, este es una variable de confusión que ha creado un gran valor atípico, y ha sesgado en gran medida el promedio de ingresos.

entonces un valor atipico puede desmadrar todos los resultados o desvalancearlos como en este ejemplo. por eso a veces la mediana puede ser preferible, es menos sensible a los valores atipicos. contrastar la mediana con tu media te puede ayudar a distinguir si en los datos tenes algun sesgo. 

## cuartil 

los cuantiles tienen el mismo concepto que la mediana, solo que en otros lugares que no son el centro de la lista.

pero estos cuantiles se distribullen cada 25% de los datos, es decir que tenemos 3 cuantiles, el cuantil del 25% del 50% y del 75%


# moda

la moda es el conjunto de valores que ocurre con mayor frecuencia. es util cuando tus datos son repretitivos 

si no se repite ningun valor no hay moda
cuando dos valores ocurren con la misma frecuencia tenemos una **bimodal**

---
# varianza y desviacion

## variacion de la **población** y desviacion estandar

es la medida de cuan dispersos estan los datos al rededor de la media de la poblacion.

se calcula promediando el cuadrado de la diferencia entre cada valor y la media de la poblacio dividido por el tamaño de la poblacion 

$$ Varianza \, de \, una \, población = \frac{(x_{1} - promedio)^2 + (x_{2} - promedio)^2 + ... + (x_{n} - promedio)^2}{N} $$Más formalmente:
$$ \sigma^2 = \frac{\sum{(x_i - \mu)^2}}{N} $$$$ \sigma = \sqrt{\frac{\sum{(x_i - \mu)^2}}{N}} $$
## varianza de la **muestra** y desviacion estandar

$$ s^2 = \frac{\sum{(x_i - \bar{x})^2}}{n-1} $$$$ s = \sqrt{\frac{\sum{(x_i - \bar{x})^2}}{n-1}} $$
cuando calculamos la varianza y la desviacion estandar para una muestra en lugar de la pobleacion dividimos por n-1 en lugar de n para compenzar el hecho de que estamos estimando la varianza de la poblaxion a aprtir de una muestra. Esta correccion ayuda a evitar la variabilidad real en la poblacion


# distribucion o camapana normal o gaussiana

la distribucion normal o gaussiana en su grafica se ve como una campana, teniendo una elevacion en el centro y los valles hacia los costados, es decir que la probabilidad de que la probabilidad aleatoria caiga al rededor de la media es muy alta y que esa probabilidad disminulle hacia los extremos .su dispersión está definida por una desviación estándar. Las "colas" a cada lado se vuelven más delgadas a medida que te alejas de la media.

## propiedades de la distribucion normal 

La distribución normal tiene varias propiedades importantes que la hacen útil:

- Es simétrica; ambos lados están identicamente reflejados en la media, que es el centro.
- La mayor parte de la masa está en el centro alrededor de la media.
- Tiene una dispersión (ya sea estrecha o amplia) que está especificada por la desviación estándar.
- Las "colas" son los resultados menos probables y se acercan a cero infinitamente pero nunca alcanzan cero.
- Se asemeja a muchos fenómenos en la naturaleza y la vida diaria, e incluso generaliza problemas no normales debido al teorema del límite central, del cual hablaremos pronto.

## la funcion de densidad de probabilidad

$$ f(x) = \frac{1}{\sigma * \sqrt{2\pi}} * e^{\frac{-{(x-\mu)}^2}{2\sigma^2}}$$

es la probabilidad relativa de que una variable aleatoria continua tome un valor dado. en otras palabras indica la densidad de probabilidad en diferentes puntos del rengo de valores posibles de la variable continua 

