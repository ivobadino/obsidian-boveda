---
tags:
  - spd
  - unidad-7
---
# que es ? 

Es el proceso mediante el cual la [[UNIDAD DE CONTROL]] determina y ejecuta la secuencia correcta de microinstrucciones para llevar a cabo una instruccion de lenguaje maquina (o instruccion de alto nivel).

Es el mecanismo dentro de la UDC que, para cada isntruccion de lenguaje maquina, bsuca en la MEMORIA DE CONTROL (donde estan almacenadas las microinstrucciones) la secuencia predefinida de microinstrucciones asociadas a esa instruccion. Luego la UDC las ejecuta una a una en el orden correcto, generando las señales de control necesatias par que los diferentes componentes de la CPU realicen las operaciones deseadas.

En resumen el secuenciamiento interno de microinstrucciones es el "director de orquesta" de la UNIDAD DE CONTROL microprogramada.  Se encarga de traducit una isntruccion compleja de lenguaje maquina en una seria de pasos diminutos y ordenados que el hardwere de la CPU puede ejecutar directamente, asegurando que cada operacion de realice en el montento y lugar precisos. Esto es clave para la flexibilidad de las UDC microprogramadas, ya que cambiar la funcionalidad de una isntruccion solo requiere mosdificar su secuencia de microinstrucciones en la memoria de control, en lugar de rediseñar circuitos fisicos.

## TIPOS DE SECUENCIAMIENTO INTERNO

De acuerdo a como de ubiquen las microintrucciones en la memoria de constrol se tendran dos tipos de secuenciamiento de las mismas.

![[Micro instrucciones#Secuenciamiento implicito]]

![[Micro instrucciones#Secuenciamineto explicito]]