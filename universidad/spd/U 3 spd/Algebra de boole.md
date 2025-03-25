---
tags:
  - spd
  - binario
  - boole
  - logica
---
# Que es la algebra de boole??

El álgebra de Boole es un sistema matemático que utiliza símbolos y reglas para representar y manipular conceptos lógicos. A diferencia del álgebra tradicional, que se enfoca en números, el álgebra de Boole trabaja con valores de "verdadero" y "falso", representados como 1 y 0, respectivamente.

**¿En qué consiste?**

El álgebra de Boole se basa en tres operaciones lógicas fundamentales:

- **AND (Y):**
    - Representa la conjunción lógica.
    - El resultado es "verdadero" (1) solo si ambas entradas son "verdaderas" (1).
- **OR (O):**
    - Representa la disyunción lógica.
    - El resultado es "verdadero" (1) si al menos una de las entradas es "verdadera" (1).
- **NOT (NO):**
    - Representa la negación lógica.
    - Invierte el valor de la entrada: "verdadero" (1) se convierte en "falso" (0) y viceversa.

**Aplicaciones:**

El álgebra de Boole es fundamental en el diseño de circuitos electrónicos digitales y en la programación de computadoras. Se utiliza para simplificar y optimizar expresiones lógicas, lo que permite crear sistemas más eficientes y confiables. 

# Expresiones logicas

![[6e774ae7f08cde0b4b35eeec7d2b5ae58942ea9fr1-592-414v2_hq.jpg]]

# OR | union logica

de manera sencilla se puede explicar como una expresión de "O" por que para que el resultado sea verdadero con que una de las entradas sea verdadera o las dos es verdadera, es decir "esta **O** esta ", en el caso que ninguna sea verdad la salida es falsa.

| A   | B   | S   |
| --- | --- | --- |
| 0   | 0   | 0   |
| 0   | 1   | 1   |
| 1   | 0   | 1   |
| 1   | 1   | 1   |

# AND | interseccion logica

se puede explicar como una expresion "Y", para que la expresion sea verdadera tiene que ser verdaderas las dos entradas, es decir "esta **Y** esta" par que el resultado sea verdadero, con que una o las dos sean falsas el resultado sera falso


| A   | B   | S   |
| --- | --- | --- |
| 0   | 0   | 0   |
| 0   | 1   | 0   |
| 1   | 0   | 0   |
| 1   | 1   | 1   |

# NOT | negacion

esta expresion logica simplemente invierte el valor de  verdadero a falso

| A   | S   |
| --- | --- |
| 1   | 0   |
| 0   | 1   |


# en que se relaciona con el [[sistema binario]]

![[sistema binario#relacion con el algebra de boole]]