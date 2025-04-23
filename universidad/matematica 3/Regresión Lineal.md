---
tags:
  - mate3
---
 una de las técnicas mas practicas en el análisis de datos es ajustar una linea a traves de los puntos de datos observados para mostrar una relacion entre dos o más variables. Una regresión intenta ajustar una funcion a los datos observados para hacer predicciones sobre nuevos datos

# ![[Linear_regression.svg]]



# regresion lineal con scikit-learn


# residuos y errores cuadrados 

el residuo es la diferencia entre la linea de la regresion y los puntos de los datos. Es el valor que se obtiene de restar el valor predicho de la variable dependiente del valor real de la variable dependiente .

tambiben se puede decir que los residuos pueden ser tomado como errores ya que reflejan cuanto se equivoca la linea de regrecion al predecir los datos.

se elevan al cuadraro los residuos ya que vamos a tener tanto residuos positivos como negativos entonces al elevarlos al cuadrado evitamos que los valores se cancelen entre si. Tambien se utiliza el cuadrado y no los valores absollutos ya que al derivar no termina funcionando bien el calculo.

# descenso de gradiente 

es un algoritmo utilizado para entrenar modelos de aprendisaje automatico y redes neuronales. su objetivo es minimizar una funcion objetivo derivando y ajustando iterativamente los paramentros del modelo.(en este caso la pendiente M y la interseccion B de la linea).

en el aprendiasaje queremos minimizar nuestra perdida  para eso el descenso de gradiente tiene una caracteristica atractiva:  la derivada parcial es esa linterna, permitiéndonos ver las pendientes para cada parámetro (en este caso _m_ y _b_). Avanzamos en direcciones para donde la pendiente desciende.Damos pasos más grandes para pendientes más pronunciadas y pasos más pequeños para pendientes menos pronunciadas.
 podemos calcular la longitud de este paso tomando una fraccion de la pendiente, esta fraccion es la taza de aprendizaje. cuanto mayor sea la taza de aprendisaje mas rapido avanzara a costa de la presicion pero cuanto menor sea la tasa de aprendizaje mas tiempo tomara entrenar y requerira mas iteraciones

# sobreajuste o varianza

ocurre cuando un modelo de regresion se ajusta a los datos demasiado exactamente. esto resulta en una perdida muy baja con los datos que ya ha visto, pero es muy probable que las predicciones de nuevos datos  sean impresisas 

