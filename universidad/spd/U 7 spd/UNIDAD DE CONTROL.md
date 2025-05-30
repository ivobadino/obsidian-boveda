---
tags:
  - UC
  - spd
  - unidad-7
---
## que es ??
es el dispositivo encargado de la coordinacion de todas las tareas para la ejecucion de las isntrucciones en formato binario.

durante la ejecucion de una instruccion la UDC generara todas las señales electricas internas necesarias para la coneccion y desconeccion de las diferentes unidades estructurales internas de la cpu y las senales electricas externas. Como por ejemplo las señales de lectrura o escritura, entre otras 

la alu realiza las operciones aritmeticas o logicas ordenadas por la unidad de control.

la unidad de control dentro tiene:
- logica secuencial 
- unidad de control de registros y decodificadoresona  s
- memoria de control
---
# UDC microprogramadas

inicialmente en antaño eran cableadas, con cables externos para cada instruccion

En cambio ahora las unidades de control son microprogramadas y los cabales fueron reemplazados por buffers que se conectan o desconectan con un 1(corriente), o se desconectan con un 0(no corriente).
Estos unos y ceros estan almacenados en la UDC
cada instruccion se ejecuta en la UDC como un conjunto de micro instrucciones. A este conjunto de lo denomina microprograma. Cada microinstruccion ocupa un ciclo de CLK
