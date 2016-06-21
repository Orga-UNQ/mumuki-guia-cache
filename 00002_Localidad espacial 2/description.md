Como vimos en el ejercicio anterior, la secuencia *ABCD, ABCE* se da por la ejecución de una instrucción que ocupa 2 celdas. Esto indica que 


## Principios de localidad
El principio de localidad espacial enuncia que las posiciones de memoria cercanas a alguna accedida recientemente son más probables de ser requeridas que las más distantes, y el principio de localidad temporal dice que cuando un programa hace referencia a una posición de memoria que contiene una instrucción, es probable que lo vuelva a hacer en poco tiempo. 


## Caso 2: instrucción de 3 celdas

Veamos ahora el caso de la instrucción `ADD [0xBBBB], 0x0010` , queestá ensamblada a partir de la celda 0BCD, entonces su código máquina ocupa las celdas: 0BCD, 0BCE, 0BCF. Por lo tanto, su ejecución produce las siguientes lecturas:

* Búsqueda de instrucción: 0BCD, 0BCE, 0BCF
* Búsqueda de operandos: BBBB 