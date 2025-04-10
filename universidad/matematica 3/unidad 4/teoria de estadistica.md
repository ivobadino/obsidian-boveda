
# [[Estadistica]]

---

La **estadística** es la práctica de **recolectar y analizar datos** para descubrir hallazgos útiles o predecir qué causa esos hallazgos.

Aunque no siempre se le reconozca, la estadística es el corazón de muchas innovaciones basadas en datos. El aprendizaje automático es una herramienta estadística que busca hipótesis posibles para correlacionar relaciones entre diferentes variables en los datos. Sin embargo, hay muchos puntos ciegos en la estadística, incluso para estadísticos profesionales.

Podemos atraparnos fácilmente en lo que dicen los datos y olvidarnos de preguntar de dónde vienen. Estas preocupaciones se vuelven aún más importantes a medida que la gran data, la minería de datos y el aprendizaje automático aceleran la automatización de algoritmos estadísticos. Por lo tanto, es importante tener una base sólida en estadística y pruebas de hipótesis para no tratar estas automatizaciones como cajas negras.

En esta sección cubriremos los fundamentos de la estadística y las pruebas de hipótesis. Comenzando con estadísticas descriptivas, aprenderemos formas comunes de resumir datos.

---
## ¿Qué significa "Data" o "datos"?

Definir "datos" puede parecer innecesario, pero es clave. Aunque los usamos constantemente, entender qué son realmente es fundamental en áreas como la inteligencia artificial, donde se dice que *"más datos"* equivale a *"más verdad"*.

Pero, ¿qué son los datos? No son importantes por sí mismos, sino por cómo los analizamos y lo que podemos descubrir con ellos.

Los datos son fotos de la realidad, capturando solo fragmentos de historias completas, y pueden estar **sesgados** o **incompletos**. En la ciencia de datos, apuntamos a recopilar datos enfocados y relevantes para nuestros objetivos, evitando caer en análisis superficiales o conjuntos de datos incompletos. Es crucial cuestionar cómo se crearon los datos y qué no están mostrando.

Aunque nos encantaría recrear la realidad con datos infinitos, la práctica nos muestra que debemos ser estratégicos y realistas sobre lo que los datos pueden y no pueden hacer. Recordar que los datos ofrecen pistas, no verdades absolutas, es vital para evitar conclusiones erróneas. Ser curioso sobre el origen y la creación de los datos es fundamental para cualquier proyecto de aprendizaje automático exitoso.

---

### Ejemplo de sesgado

Imaginemos que queremos determinar si alguien es bueno jugando al fútbol basándonos en unas pocas fotos estratégicas.

Si tienes una foto de él ejecutando un tiro libre con técnica impecable, podrías suponer que tiene buena habilidad. O si hay una imagen celebrando un gol, podrías inferir que es un buen jugador.

Incluso podrías considerar una foto de la planilla del partido con sus estadísticas. Sin embargo, es crucial recordar que todas estas instancias pueden ser engañosas o sacadas de contexto.

Tal vez estaba celebrando el gol de otro, o la planilla no era suya o estaba alterada.

Así como con estas fotos, los datos no capturan el contexto completo ni las explicaciones, ofreciendo pistas que pueden llevarnos a la verdad o desviarnos hacia conclusiones erróneas.

Este enfoque crítico es vital, especialmente en la era del big data y el aprendizaje automático, donde la tentación de tomar los datos al pie de la letra sin cuestionar su origen es grande.

---
### Tipos de sesgos

---

Existen diferentes tipos de sesgos en estadística que pueden dificultar la interpretación precisa de los datos. Sesgo estadístico es un término usado para describir estadísticas que no proporcionan una representación precisa de la población.

- Sesgo de confirmación: El sesgo de confirmación ocurre cuando dejamos que nuestras creencias previas influyan en cómo priorizamos o interpretamos la información. Por ejemplo, si creemos firmemente que la mayoría de las personas prefieren el helado de vainilla sobre el de chocolate, podríamos prestar más atención a los datos que respaldan esa idea, ignorando información contraria.
    
- Sesgo de selección: El sesgo de selección es un error que se deriva de usar muestras de población que no representen con precisión a todo el grupo objetivo.
    
- Sesgo del caso atípico: Los valores atípicos pueden distorsionar considerablemente los datos. Por ejemplo, al examinar los ingresos en los Estados Unidos, unas pocas personas extremadamente ricas pueden distorsionar los cálculos de los promedios. Por esta razón, la mediana suele ser una representación más precisa de la población en general.
    
- Sesgo del observador: El sesgo del observador es un tipo de sesgo estadístico que surge de la subjetividad inherente al observador. Dado que es imposible ser completamente imparcial, el sesgo del observador siempre representa un desafío. La mejor manera de abordarlo es aprender a identificarlo.
    
- Sesgo de financiación: El sesgo de financiación se refiere a la tendencia de un estudio a favorecer a la entidad que lo financió. Estos estudios suelen generar datos sesgados, lo que puede dificultar su aplicabilidad en tu negocio.
    
- Sesgo de variable omitida: El sesgo de variable omitida ocurre cuando la ausencia de una variable relevante afecta la validez de los resultados estadísticos. Por ejemplo, un estudio sobre automóviles que no considera el año o el kilometraje puede arrojar resultados imprecisos. Este tipo de sesgo es común en las estadísticas y puede llevar a conclusiones erróneas. Al analizar datos, es importante asegurarse de que se incluyan todas las variables relevantes para obtener resultados más precisos.
    
- Sesgo del superviviente: El sesgo del superviviente ocurre cuando solo se consideran los datos de aquellos que sobreviven o tienen éxito en una determinada situación. Al no tener en cuenta todas las fuentes potenciales de datos, se puede obtener una representación incompleta o sesgada de la realidad.
    

---

---

### Verdad absoluta

Hablando en términos más amplios, el ejemplo de "las fotos jugando al fútbol" presenta un problema de verdad absoluta o "ground truth".

Si vamos al caso de la **seguridad de sistemas de inteligencia artificial**, hay una pregunta que se suele hacer para los autos autónomos sean más seguros:

“Cuando un auto autónomo no logra reconocer a un peatón con su cámara, ¿no hay manera de que reconozca el fallo y se detenga?”

Tratemos de responderla juntos.

---

La respuesta es que no, porque el sistema no tiene un marco para la verdad absoluta, o conocimiento verificado y completo de lo que es verdadero.  
Si el auto falla en reconocer a un peatón, ¿cómo se supone que reconozca que está fallando en reconocer a un peatón?  
No hay una verdad absoluta en la que apoyarse, a menos que haya un operador humano que pueda proporcionarla e intervenir.

Este es, de hecho, el estado actual de los autos y servicios de taxi "autónomos". Algunos sensores como el radar proporcionan verdades absolutas moderadamente confiables sobre preguntas específicas, como "¿Hay algo frente al vehículo?" Pero reconocer objetos basados en sensores de cámara y LIDAR (en un ambiente no controlado) es un problema de percepción mucho más difuso con números astronómicos de combinaciones de píxeles que podría ver. Así, la verdad absoluta es inexistente.

¿Tu data representa una verdad absoluta que es verificable y completa? ¿Son los sensores y fuentes confiables y precisos? ¿O es la verdad absoluta desconocida?

---

keyboard_arrow_down

## Estadística Inferencial vs Descriptiva

---

¿Qué te viene a la mente cuando escuchás la palabra “estadísticas”?

La parte más comúnmente entendida de las estadísticas es el análisis de los datos para condensarlos y describirlos, llamada **estadística descriptiva**. Después de todo, ¿es más significativo desplazarse por un millón de registros de datos o tenerlos resumidos? Esta es la parte de la estadística en la que vamos a ahondar en esta materia.

Las **estadísticas inferenciales**, por otro lado, intentan descubrir atributos sobre una población más grande, a menudo basada en una muestra. Suele ser mal entendida y menos intuitiva que las estadísticas descriptivas.

Pero la razón de ser de este tipo de estadística es porque frecuentemente estamos interesados en estudiar un grupo que es demasiado grande para observar (por ejemplo, la altura promedio de los adolescentes en San Martín) y tenemos que recurrir a usar solo unos pocos miembros de ese grupo para inferir conclusiones sobre ellos.

Esto no es fácil de hacer correctamente. Después de todo, estamos intentando representar una población con una muestra que puede **no ser representativa**.

---

## Poblaciones, muestras y sesgo

Antes de meternos más en estadísticas descriptivas e inferenciales, es una buena idea definir algunos términos con ejemplos más cercanos.

Una población es un grupo específico que queremos estudiar, como “todos los jubilados mayores de 65 en Argentina”, “todos los perros de raza Labrador en Buenos Aires”, o “estudiantes de segundo año del Colegio Nacional Buenos Aires”.  
Fijate cómo definimos los límites de nuestra población. Algunos límites son amplios y capturan un grupo grande, otros son específicos y pequeños como los estudiantes de un colegio en particular. Cómo definís una población depende de lo que te interese estudiar.

Una muestra es un subconjunto de la población que idealmente es aleatorio y sin sesgo, que usamos para inferir atributos sobre la población. A menudo estudiamos muestras porque encuestar a toda la población no siempre es posible. Claro, algunas poblaciones son más accesibles si son pequeñas. ¿Pero medir a todos los jubilados mayores de 65 en Argentina? ¡Eso probablemente no sea práctico!

Si vamos a inferir atributos de una población basada en una muestra, es importante que esta sea lo más aleatoria posible para no sesgar nuestras conclusiones. Por ejemplo, si soy estudiante en la UNSAM y quiero encontrar cuántas horas los universitarios ven la tele por semana en Argentina. Salgo de al recreo y empiezo a encuestar estudiantes al azar, terminando mi recolección de datos bastante rápido. ¿Cuál es el problema?

El problema es que nuestra muestra de estudiantes va a tener sesgo, lo que distorsiona nuestros hallazgos sobrerrepresentando un grupo en detrimento de otros. Mi estudio definió la población como “estudiantes universitarios en Argentina”, no “estudiantes de la UNSAM”. ¡Estoy encuestando estudiantes de una universidad específica para representar a todos los universitarios del país!

Es poco probable que todas las universidades del país tengan los mismos atributos en sus estudiantes. ¿Y si los estudiantes de la UNSAM ven más tele que otros? ¿Usarlos para representar a todo el país no distorsionaría los resultados?

Esto es solo una variable posible que muestra por qué es mala idea representar a todos los universitarios del país con una muestra de una universidad. Idealmente, debería encuestar aleatoriamente a estudiantes universitarios de todo el país en diferentes universidades.

Sin embargo, el sesgo no siempre es geográfico. Digamos que hago un esfuerzo sincero para encuestar estudiantes a través del país. Organizo una campaña en redes sociales para que se comparta una encuesta. Consigo cientos de respuestas sobre los hábitos de ver tele de estudiantes y siento que he vencido al sesgo... ¿o no?

¿Y si los estudiantes que están en redes sociales y ven la encuesta también son más propensos a ver más tele? Este tipo de sesgo, donde un grupo específico es más probable que se incluya en una muestra, se conoce como sesgo de autoselección.

¡Rayos! Parece que no se puede ganar, ¿no? Si lo pensás lo suficiente, el sesgo en los datos parece inevitable. Y a menudo lo es. Tantos factores confusos pueden influir en nuestro estudio. Este problema de sesgo en los datos es caro y difícil de superar, y el aprendizaje automático es especialmente vulnerable a él.

La forma de superar este problema es seleccionar verdaderamente al azar estudiantes de toda la población, y ellos no pueden elegirse voluntariamente para entrar o salir de la muestra. Esta es la forma más efectiva de mitigar el sesgo, pero como podés imaginar, requiere muchos recursos coordinados para hacerlo.

Bueno, basta de hablar sobre poblaciones, muestras y sesgos. Pasemos a algunas matemáticas y estadísticas descriptivas. Solo recordá que las matemáticas y las computadoras no reconocen el sesgo en tus datos. Eso depende de ti, como buen profesional de la ciencia de datos, detectarlo. Siempre hacé preguntas sobre cómo se obtuvieron los datos y luego examiná cómo ese proceso podría haber sesgado los datos.

---

keyboard_arrow_down

## Promedio y promedio ponderado

---

El promedio es la media de un conjunto de valores. La operación es simple de realizar: sumar los valores y dividirlos por la cantidad de valores. El promedio es útil porque muestra dónde se encuentra el "centro de gravedad" para un conjunto observado de valores.

El promedio se calcula de la misma manera tanto para poblaciones como para muestras.

---

[ ]

sample = [1, 3, 2, 5, 7, 0, 2, 3]  
  
mean = sum(sample) / len(sample)  
  
print(mean)  

---

En el ejemplo, observamos a ocho personas y les preguntamos cuántas mascotas tienen. Sumamos las respuestas y las dividimos entre el número total de personas encuestadas, lo que nos da un promedio de 2.875 mascotas por persona.

---

Hay dos versiones del promedio o media: el promedio o media muestral

x¯=x1+x2+x3+...+xnn=∑xin

y la media poblacional o simplemente promedio

μ=x1+x2+x3+...+xnN=∑xiN

La _n_ la _N_ representan el tamaño de la muestra y de la población, respectivamente, pero matemáticamente representan lo mismo: el número de elementos. Lo mismo ocurre al llamar a la media de la muestra *"x-barra"* y a la media poblacional _μ_: son el mismo cálculo, simplemente tienen nombres diferentes dependiendo de si estamos trabajando con una muestra o una población.

En resumen, el promedio muestral se basa en una muestra representativa de la población y se utiliza para estimar la media poblacional, que es el valor promedio verdadero de toda la población.

---

Es probable que estés familiarizado con el promedio, pero el promedio o media es en realidad un promedio ponderado llamado media ponderada. El proemdio que usamos comúnmente da igual importancia a cada valor. Pero podemos manipular el promedio y darle a cada elemento un peso diferente:

PromedioPonderado=(x1⋅w1)+(x2⋅w2)+(x2⋅w2)+...+(xn⋅wn)w1+w2+w3+...+wn

Esto puede ser útil cuando queremos que algunos valores contribuyan más a la media que otros. Un ejemplo común de esto es la ponderación de los exámenes académicos para calcular una nota final. Si tienes tres exámenes y un examen final, y asignamos un peso del 20% a cada uno de los tres exámenes y un peso del 40% al examen final para la nota final, podemos expresarlo como se muestra en el ejemplo que sigue.

---

[ ]

# Tres examenes de .20 de peso cada uno y un examen final con .40 de peso

sample = [90, 80, 63, 87]

weights = [.20, .20, .20, .40]

weighted_mean = sum(s * w for s,w in zip(sample, weights)) / sum(weights)

print(weighted_mean)

81.4

---

En resumen, al aplicar pesos diferentes a cada puntaje de examen, podemos ajustar su contribución al promedio final. Esto nos permite dar más importancia a ciertos exámenes sobre otros al calcular el promedio. Los pesos pueden ser cualquier número, ya que al final se ajustarán proporcionalmente. En el ejemplo que sigue veremos que tenemos el resultado si los tres examenes tienen un peso de 1.0 y el examen final tiene un peso de 2.0.

---

[ ]

sample = [90, 80, 63, 87]

weights = [1.0, 1.0, 1.0, 2.0]

weighted_mean = sum(s * w for s,w in zip(sample, weights)) / sum(weights)

print(weighted_mean)

81.4

---

keyboard_arrow_down

## Mediana

---

La mediana es el valor que está en el medio de un conjunto de datos ordenados. Si el conjunto de datos tiene un número impar de elementos, la mediana es simplemente el valor central. Sin embargo, si el conjunto tiene un número par de elementos, la mediana es el promedio de los dos valores centrales.

En el ejemplo proporcionado, la mediana es 7, lo que significa que la mitad de las personas encuestadas tienen 7 o menos mascotas, y la otra mitad tiene 7 o más.

0, 1, 5, **7**, 9, 10, 14

---

[ ]

# Cantidad de mascotas que tiene cada persona  
sample = [0, 1, 5, 7, 9, 10, 14]  
  
def median(values):  
    ordered = sorted(values)  
    print(ordered)  
    n = len(ordered)  
    mid = int(n / 2) - 1 if n % 2 == 0 else int(n/2)  
  
    if n % 2 == 0:  
        return (ordered[mid] + ordered[mid+1]) / 2.0  
    else:  
        return ordered[mid]  
  
print(median(sample))  

[0, 1, 5, 7, 9, 10, 14]
7

---

La mediana puede ser una alternativa útil al promedio cuando los datos están sesgados por valores atípicos, es decir, valores que son extremadamente grandes o pequeños en comparación con el resto de los valores.

Una anécdota interesante para entender este concepto es la siguiente. En 1986, el salario inicial anual promedio de los graduados en geografía de la Universidad de Carolina del Norte en Chapel Hill fue de 250,000.Otrasuniversidadespromediaron22,000. ¿Por qué? Bueno... Michael Jordan fue uno de los graduados de la UNC. Uno de los jugadores de la NBA más famosos de todos los tiempos realmente se graduó con un título en geografía de UNC. Sin embargo, comenzó su carrera jugando al baloncesto, no estudiando mapas. Obviamente, este es una variable de confusión que ha creado un gran valor atípico, y ha sesgado en gran medida el promedio de ingresos.

Por eso la mediana puede ser preferible en situaciones con muchos valores atípicos (como datos relacionados con ingresos) en lugar de la media o promedio. Es menos sensible a los valores atípicos y divide los datos estrictamente por la mitad según su orden relativo, en lugar de dónde caen exactamente en una línea numérica. Cuando tu mediana es muy diferente de tu media, eso significa que tienes un conjunto de datos sesgado con valores atípicos.

---

**La mediana es un cuantil** Existe un concepto de cuantiles en estadísticas descriptivas. El concepto de cuantiles es esencialmente lo mismo que el de una mediana, solo que corta los datos en otros lugares además del centro. La mediana es en realidad el cuantil del 50%, o el valor donde el 50% de los valores ordenados están detrás de él. Luego están los cuantiles del 25%, 50% y 75%, que se conocen como cuartiles porque cortan los datos en incrementos del 25%.

---

keyboard_arrow_down

## Moda

---

La moda es el conjunto de valores que ocurre con mayor frecuencia. Principalmente resulta útil cuando tus datos son repetitivos y deseas encontrar qué valores ocurren con mayor frecuencia.

Cuando ningún valor ocurre más de una vez, no hay moda. Cuando dos valores ocurren con la misma frecuencia, entonces el conjunto de datos se considera bimodal. En el ejemplo siguiente calculamos la moda para nuestro conjunto de datos de mascotas, y efectivamente vemos que es bimodal ya que tanto 2 como 3 ocurren con la misma frecuencia y más a menudo.

---

[ ]

# Cantidad de mascotas que tiene cada persona  
from collections import defaultdict  
  
sample = [1, 3, 2, 5, 7, 0, 2, 3]  
  
def mode(values):  
    counts = defaultdict(lambda: 0)  
  
    for s in values:  
        counts[s] += 1  
  
    max_count = max(counts.values())  
    modes = [v for v in set(values) if counts[v] == max_count]  
    return modes  
  
print(mode(sample))  

[2, 3]

---

En la práctica, la moda no se utiliza mucho a menos que tus datos sean repetitivos. Esto se encuentra comúnmente con enteros, categorías y otras variables discretas.

---

keyboard_arrow_down

## Varianza y Desviación Estándar

---

keyboard_arrow_down

### Variación de la población y desviación estándar

---

Cuando empezamos a hablar sobre la varianza y la desviación estándar, es donde se pone interesante. Una cosa que confunde a la gente con la varianza y la desviación estándar es que hay algunas diferencias en los cálculos para la muestra versus la población.

Al describir datos, a menudo estamos interesados en medir las diferencias entre la media y cada punto de datos. Esto nos da una idea de qué tan "dispersos" están los datos.

Digamos que estoy interesado en estudiar la cantidad de mascotas que tienen los miembros de mi personal laboral (definiendo esto como mi población, no como una muestra). Tengo siete personas en mi personal.

Calculo la media de todas las cantidades de mascotas que poseen, y obtengo 6.571. Ahora, sustrayamos esta media de cada valor. Esto nos mostrará cuánto se aleja cada valor de la media, como se muestra en la Tabla.

---

|Valor|Promedio|Diferencia|
|:-:|:-:|:-:|
|0|6.571|-6.571|
|1|6.571|-5.571|
|5|6.571|-1.571|
|7|6.571|0.429|
|9|6.571|2.429|
|10|6.571|3.429|
|14|6.571|7.429|

---

Veamos esto en un gráfico:

---

Ahora considera por qué esta información puede ser útil. Las diferencias nos dan una idea de cuán dispersos están los datos y qué tan lejos están los valores de la media. ¿Hay alguna forma de consolidar estas diferencias en un solo número para describir rápidamente cuán dispersos están los datos?

Puedes sentirte tentado a tomar el promedio de las diferencias, pero los negativos y positivos se cancelarán entre sí cuando se sumen. Podríamos sumar los valores absolutos (eliminar los signos negativos y hacer que todos los valores sean positivos). Una mejor aproximación sería elevar al cuadrado estas diferencias antes de sumarlas. Esto no solo elimina los valores negativos (porque elevar al cuadrado un número negativo lo hace positivo), sino que también amplifica las diferencias más grandes y es matemáticamente más fácil de trabajar. Después de eso, calcula el promedio de las diferencias al cuadrado. Esto nos dará la varianza, una medida de cuán dispersos están nuestros datos.

Varianzadeunapoblación=(x1−promedio)2+(x2−promedio)2+...+(xn−promedio)2N

Más formalmente:

σ2=∑(xi−μ)2N

---

[ ]

# Cantidad de mascotas que tiene cada persona  
data = [0, 1, 5, 7, 9, 10, 14]  
  
def variance(values):  
    mean = sum(values) / len(values)  
    _variance = sum((v - mean) ** 2 for v in values) / len(values)  
    return _variance  
  
print(variance(data))  

21.387755102040817

---

Entonces, la varianza para el número de mascotas propiedad de mi personal de oficina es 21.387755. Bueno, ¿pero qué significa exactamente? Es razonable concluir que una varianza más alta significa una mayor dispersión, pero ¿cómo relacionamos esto con nuestros datos? Este número es más grande que cualquiera de nuestras observaciones porque hicimos muchas elevaciones al cuadrado y sumas, lo que lo coloca en una métrica completamente diferente. Entonces, ¿cómo lo reducimos para que vuelva a la escala con la que comenzamos?

La operación opuesta de elevar al cuadrado es la raíz cuadrada, así que tomemos la raíz cuadrada de la varianza, lo que nos da la desviación estándar. Esto es la varianza escalada en un número expresado en términos de "número de mascotas", lo que lo hace un poco más significativo:

σ=∑(xi−μ)2N−−−−−−−−−−√

---

[ ]

from math import sqrt  
  
# Cantidad de mascotas que tiene cada persona  
data = [0, 1, 5, 7, 9, 10, 14]  
  
def variance(values):  
    mean = sum(values) / len(values)  
    _variance = sum((v - mean) ** 2 for v in values) / len(values)  
    return _variance  
  
def std_dev(values):  
    return sqrt(variance(values))  
  
print(std_dev(data))  

4.624689730353899

---

Al ejecutar el código en el ejemplo, verás que nuestra desviación estándar es aproximadamente de 4.62 mascotas. Así que podemos expresar nuestra dispersión en una escala con la que empezamos, lo que hace que nuestra varianza sea un poco más fácil de interpretar.

---

keyboard_arrow_down

### Varianza de la muestra y desviación estándar

---

En la sección anterior hablamos sobre la varianza y la desviación estándar para una población. Sin embargo, hay un ajuste importante que debemos aplicar a estas dos fórmulas cuando calculamos para una muestra:

s2=∑(xi−x¯)2n−1

s=∑(xi−x¯)2n−1−−−−−−−−−−√

Cuando calculamos la varianza y la desviación estándar para una muestra en lugar de una población, dividimos por n-1 en lugar de n para compensar el hecho de que estamos estimando la varianza de la población a partir de una muestra. Esta corrección ayuda a evitar subestimar la variabilidad real en la población.

---

Si nuestros datos sobre mascotas fueran una muestra en lugar de una población, deberíamos hacer ese ajuste en consecuencia.

---

[ ]

from math import sqrt  
  
# Cantidad de mascotas que tiene cada persona  
data = [0, 1, 5, 7, 9, 10, 14]  
  
# Se agrega el parametro is_sample para saber si es una muestra y restar 1 en el denominador  
def variance(values, is_sample: bool = False):  
    mean = sum(values) / len(values)  
    _variance = sum((v - mean) ** 2 for v in values) / (len(values) - (1 if is_sample else 0))  
    return _variance  
  
  
def std_dev(values, is_sample: bool = False):  
    return sqrt(variance(values, is_sample))  
  
  
print("VARIANCE = {}".format(variance(data, is_sample=True)))  
print("STD DEV = {}".format(std_dev(data, is_sample=True)))  

VARIANCE = 24.952380952380953
STD DEV = 4.995235825502231

---

Observa en el ejemplo que mi varianza y desviación estándar han aumentado en comparación con ejemplos anteriores que las trataban como una población, no como una muestra. Recuerda que antes, la desviación estándar fue aproximadamente 4.62 tratándola como una población. Pero aquí, tratándola como una muestra (al restar 1 del denominador de la varianza), obtenemos aproximadamente 4.99. Esto es correcto, ya que una muestra podría estar sesgada e imperfecta al representar la población. Por lo tanto, aumentamos la varianza (y, por lo tanto, la desviación estándar) para aumentar nuestra estimación de cuán dispersos están los valores. Una varianza/desviación estándar más grande muestra menos confianza con un rango más grande.

---

keyboard_arrow_down

## La Distribución Normal

---

Una distribución de probabilidad es una descripción matemática de las posibles ocurrencias de un evento aleatorio. Es una función que asigna a cada evento una probabilidad de que ocurra. Las distribuciones de probabilidad se utilizan para modelar una amplia variedad de fenómenos en áreas como la estadística, la física, la ingeniería, la economía y muchas otras disciplinas. Una distribución de probabilidad puede ser discreta, donde los eventos tienen valores discretos y a menudo se representan como histogramas o tablas, o continua, donde los eventos pueden tener valores en un intervalo continuo y se representan mediante funciones de densidad de probabilidad.

---

La distribución normal, también conocida como distribución gaussiana, es una distribución simétrica en forma de campana que tiene la mayor concentración alrededor de la media, y su dispersión está definida por una desviación estándar. Las "colas" a cada lado se vuelven más delgadas a medida que te alejas de la media.

La siguiente figura es una distribución normal para los pesos de los golden retriver. Observa cómo la mayor parte de la masa se encuentra alrededor de la media de 64.43 lb.

---

keyboard_arrow_down

### Descubriendo la Distribución Normal

---

La distribución normal se observa mucho en la naturaleza, la ingeniería, la ciencia y otros campos. ¿Cómo la descubrimos? Digamos que tomamos una muestra del peso de 50 golden retrievers adultos y los representamos en una línea numérica como se muestra en la siguiente figura.

---

Tenemos más valores hacia el centro, pero a medida que nos movemos más a la izquierda o a la derecha vemos menos valores. Según nuestra muestra, parece muy poco probable que veamos un golden retriever con un peso de 57 o 71 libras. ¿Pero tener un peso de 64 o 65 libras? Sí, ciertamente parece probable.

¿Hay una mejor manera de visualizar esta probabilidad para ver qué pesos de golden retriever son más probables de encontrar en una muestra de la población? Podemos intentar crear un histograma, que agrupa los valores en rangos numéricos de longitud igual y luego utiliza un gráfico de barras que muestra el número de valores dentro de cada rango.

---

El histograma actual no muestra claramente la distribución de nuestros datos debido a que los intervalos son demasiado pequeños. Dado que no tenemos una gran cantidad de datos, necesitamos agrandar los intervalos para obtener una representación más clara de cómo están distribuidos los pesos de los golden retrievers en nuestra muestra. Vamos a aumentar el tamaño de los intervalos a tres libras cada uno.

---

¡Ahora estamos avanzando! Como puedes ver, si ajustamos el tamaño de los intervalos correctamente (en este caso, cada uno tiene un rango de tres libras), comenzamos a obtener una forma de campana significativa en nuestros datos. No es una forma de campana perfecta porque nuestras muestras nunca van a ser perfectamente representativas de la población, pero este es probablemente un indicio de que nuestra muestra sigue una distribución normal. Si ajustamos un histograma con tamaños de intervalos adecuados y lo escalamos para que tenga un área de 1.0 (que es lo que requiere una distribución de probabilidad), veremos una curva de campana aproximada que representa nuestra muestra.

---

Al observar esta curva de campana, razonablemente podemos esperar que un golden retriever tenga un peso más probable alrededor de 64.43 (la media), pero poco probable en 55 o 73. Cualquier valor más extremo que eso se vuelve muy improbable.

---

keyboard_arrow_down

### Propiedades de la Distribución Normal

---

La distribución normal tiene varias propiedades importantes que la hacen útil:

- Es simétrica; ambos lados están identicamente reflejados en la media, que es el centro.
    
- La mayor parte de la masa está en el centro alrededor de la media.
    
- Tiene una dispersión (ya sea estrecha o amplia) que está especificada por la desviación estándar.
    
- Las "colas" son los resultados menos probables y se acercan a cero infinitamente pero nunca alcanzan cero.
    
- Se asemeja a muchos fenómenos en la naturaleza y la vida diaria, e incluso generaliza problemas no normales debido al teorema del límite central, del cual hablaremos pronto.
    

---

keyboard_arrow_down

### La función de Densidad de Probabilidad (PDF)

---

La función de densidad de probabilidad (PDF, por sus siglas en inglés) es una función que describe la probabilidad de que una variable aleatoria caiga dentro de un rango particular de valores. En otras palabras, proporciona una descripción de la distribución de probabilidad de una variable continua. La PDF no da la probabilidad directa de que ocurra un evento específico, sino que indica la densidad de probabilidad en diferentes puntos del rango de valores posibles. Esta función es fundamental en la teoría de la probabilidad y se utiliza ampliamente en estadísticas y análisis de datos para modelar y comprender la distribución de variables aleatorias continuas.

---

La desviación estándar juega un papel importante en la distribución normal, porque define qué tan "extendida" está. En realidad, es uno de los parámetros junto con la media. La función de densidad de probabilidad (PDF) que crea la distribución normal es la siguiente, donde _x_ es la variable aleatoria, μ es la media y σ la desviación estándar:

f(x)=1σ∗2π−−√∗e−(x−μ)22σ2

Así podemos expresarlo en Python:

---

[ ]

# Distribución normal, devuelve probabilidad

import math

def normal_pdf(x: float, mean: float, std_dev: float) -> float:

    return (1.0 / (2.0 * math.pi * std_dev ** 2) ** 0.5) * math.exp(-1.0 * ((x - mean) ** 2 / (2.0 * std_dev ** 2)))

---

arrow_upward

arrow_downward

link

comment

edit

delete

more_vert

Hay mucho que desentrañar en esta fórmula, pero lo importante es que acepta una media y una desviación estándar como parámetros, así como un valor de x para que puedas buscar la probabilidad en ese valor dado.

La distribución normal es continua. Esto significa que para obtener una probabilidad necesitamos integrar un rango de valores de x para encontrar un área.

En la práctica, sin embargo, usaremos SciPy para hacer estos cálculos por nosotros.

---

keyboard_arrow_down

# Ejercicio para aplicar conceptos

---

Analicemos los siguientes datos que corresponden al precio de la hamburguesa Big Mac en enero del año 2022 en distintos países del mundo. Los precios están en dólares estadounidenses, convertidos con la tasa de cambio de cada país.

Hacer un programa en Python que haga el siguiente análisis estadístico:

1. Obtener el costo medio de un Big Mac en los países seleccionados.
2. Encontrar el valor medio de la muestra. Observar los datos, ¿hay valores atípicos?
3. ¿Cuál es el precio más común del Big Mac?
4. ¿Cuánto varían los precios en relación con el valor medio o promedio?
5. Graficar en un histograma los datos. Agregar etiquetas y títulos al gráfico.

---

[Productos de pago de Colab](https://colab.research.google.com/signup?utm_source=footer&utm_medium=link&utm_campaign=footer_links) - [Cancelar contratos](https://colab.research.google.com/cancel-subscription)

fiber_manual_record

close