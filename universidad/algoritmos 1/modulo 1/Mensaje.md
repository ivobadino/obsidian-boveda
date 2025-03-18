---
tags:
  - mensaje
  - metodo
  - identidad
  - propiedad
  - algoritmos1
---
## que es?

Son la forma que permite a los [[Objeto | objetos]] interactuar entre si y con el ambiente. Es la solicitud que recibe un objeto para que ejecute un[[Método]] que puede ser proveniente de otro objeto o del ambiente. Es la forma en la que un objeto le dice a otro "realiza esta terea"

 Los mensajes están definidos por estos conceptos: 
 - solicitud de acción
 - comunicación entre objetos
 - llamada a métodos

## como esta compuesto 

- **Objeto receptor:**
    - Es el objeto al que se envía el mensaje, el que debe realizar la acción.
    
- **Método:**
    - Es la acción específica que se solicita al objeto receptor.
    
- **Argumentos (opcional):**
    - Son los datos adicionales que el objeto emisor proporciona al objeto receptor para que pueda realizar la acción.

## importancia de los mensajes:

#### modularidad :
- Los mensajes fomentan la modularidad al permitir que los objetos interactúen sin necesidad de conocer los detalles internos de cada uno.

#### encapsulamiento:
- Los mensajes permiten que los objetos mantengan su estado interno protegido, ya que solo pueden ser modificados a través de los métodos expuestos.

#### flexibilidad:
- Los mensajes permiten que los objetos respondan de manera diferente a la misma solicitud, lo que facilita el polimorfismo.

## como interactuan los objetos

1. tengo que conocer al #objeto .
2. al conocer al #objeto se que mensaje le puedo mandar.
3. no tengo que saber como lo hace, solo saber que es lo que hace  para evitar involucrarme en el como sino solo en el resultado que me de este metodo. 
4. utilizar la [[Abstraccion]] 

![[modulo1.pdf#page=5]]

## tipos de mensajes

![[Método#disparadores]]

---
## conclusión
