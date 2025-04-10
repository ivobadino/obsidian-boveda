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

# promedio y promedio ponderado
Hay dos versiones del promedio o media: 

el promedio o media muestral
$$ \bar{x} = \frac{x_{1}+x_{2}+x_{3}+...+x_{n}}{n} = \displaystyle\sum_{}\frac{x_{i}}{n} $$y la media poblacional o simplemente promedio
$$ \mu = \frac{x_{1}+x_{2}+x_{3}+...+x_{n}}{N} = \displaystyle\sum_{}\frac{x_{i}}{N} $$

son la misma cuenta pero depende en que se usen cambia el nombre.

N o n representan el tamano de la muestra y de la poblacion

### promedio ponderado

$$ Promedio Ponderado = \frac{(x_{1} \cdot w_{1}) + (x_{2} \cdot w_{2}) + (x_{2} \cdot w_{2}) + ... + (x_{n} \cdot w_{n})}{w_{1}+w_{2}+w_{3}+...+w_{n}} $$

