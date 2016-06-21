Como vimos en el ejercicio anterior, la secuencia *ABCD, ABCE* se da por la ejecución de una instrucción que ocupa 2 celdas. 

Veamos ahora el caso de la instrucción `ADD [0xBBBB], 0x0010` , que está ensamblada a partir de la celda 0BCD, entonces su código máquina ocupa las celdas: 0BCD, 0BCE, 0BCF. Por lo tanto, su ejecución produce las siguientes lecturas:

* Búsqueda de instrucción: 0BCD, 0BCE, 0BCF
* Búsqueda de operandos: BBBB 

### Pongamos en práctica

> ¿Que secuencia de lecturas se piden a memoria principal en el siguiente programa? (Asumir que está ensamblado a partir de la celda AAAA

```
ADD R3,[0x5656]
MOV R5, R3
SUB R5,[0x8888]
```