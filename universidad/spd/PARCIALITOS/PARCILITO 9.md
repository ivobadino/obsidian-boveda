---
tags:
  - spd
---
1. La instrucción INT XXh ,Ejecuta el servicio de la interrupción del Tipo=XXh

2. Afirmaciones  respecto de las pseudointerrupciones
	1. Son instrucciones, 
	2. Son predecibles, 
	3. No respetan ningún esquema de prioridades, 
	4. Se anidan siempre , 
	5. No ejecutan el ciclo de INTA

3. características de una estrategia de gestión centralizada de interrupciones:
	1. La CPU pregunta de a un periférico por vez,
	2. Se consulta el puerto de estado dentro del programa principal y se implementan saltos condicionados para la atención,
	3. Mientras la CPU atiende a un dispositivo, ningún otro puede ser atendido
	4. El anidamiento es por software,
	5. No requiere hardware específico para la atención de dispositivos

4. ¿Por qué decimos que hay interrupciones de hardware que son enmascarables?
	1. Porque su atención está condicionada al interrupt flag, que debe estar en 1

5.  respuestas correctas según se divide el IVT:
	1. Tipo 00h a tipo 04h son dedicadas,
	2. Tipo 05h a tipo 1Fh son reservadas,
	3. Tipo 20h a tipo FFh son disponibles

6. La interrupción por trampa se activa de la siguiente forma
	PUSHF
	POP AX
	OR AX, **ZZZZh**
	PUSH AX
	POPF
	Si el bit de trampa es el bit 8, ¿Qué máscara hexadecimal se coloca en **ZZZZh**?: ==0100==
	
7.  COMPLETAR
	1. Tipo 01h es: → Single Step - Ejecución paso a paso,
	2. Tipo 04h es: → Overflow - Desbordamiento,
	3. Tipo 00h es: → Divide error - Error división por cero,
	4. Tipo 03h es: → Breakponint - Ruptura de programas,
	5. Tipo 02h es: → Non Maskable Interrupt - Interrupción no enmascarable

8. Afirmaciones
	1. EL IVT comienza en la posición 00000h,
	2. Para cada entrada del IVT hay 4 bytes,
	3. Cada entrada del IVT posee un puntero a la ISR,
	4. Para encontrar la base de la entrada en el IVT, debo multiplicar el tipo x 4

9.  La interrupción por error sucede cuando la ALU ejecuta una división por FFh: ==*FALSO*==

10. ¿Qué significa que una interrupción por hardware no es **_incondicional_** ni **_inmediata_**?
	1. Para ser reconocida, el Interrupt Flag debe estar en 1 y la solicitud será evaluada en el último pulso de reloj de la instrucción en curso

11. Al producirse una excepción en la ALU debida a una división por 0 (cero), ¿Qué ISR se ejecutará? : 
	1. ==00h==

12.  ¿Con qué instrucción se deberá finalizar una ISR para que devuelva el control a la rutina interrumpida?
	1. ==IRET==

13. La solicitud de una interrupción se efectuará de la siguiente manera:
	1. Un flanco ascendente en la entrada INTR del procesador

14.  El ciclo de interrupción tiene las siguientes etapas, enunciándolas en forma cronológica:
	1. Solicitud, Reconocimiento, Atención, Retorno