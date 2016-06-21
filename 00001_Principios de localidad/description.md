# Accesos a memoria principal

Durante la ejecución de un programa se accede a memoria con un criterio que no es aleatorio, pero tampoco absolutamente predecible. Los accesos respetan cierta lógica que tiene relación con la naturaleza de la **ejecución de los programas**, donde se pueden distinguir dos tipos de accesos a memoria: 
* por lectura de instrucciones y 
* por lectura de datos.

La lectura de instrucciones es en su mayoría un recorrido de celdas consecutivas de memoria, y asi mismo lo es la lectura de los datos de un arreglo también. Por otro lado, las instrucciones de una rutina o de una repetición se espera que sean utilizadas más de una vez. 

Estos patrones de acceso se describen con el nombre de **principios de localidad**.

## Principios de localidad

El principio de **localidad espacial** enuncia que las posiciones de memoria cercanas a alguna accedida recientemente son más probables de ser requeridas que las más distantes, y el principio de **localidad temporal** dice que cuando un programa hace referencia a una posición de memoria que contiene una instrucción, es probable que lo vuelva a hacer en poco tiempo. 

Por ejemplo, si la instrucción `ADD [0xBBBB], 0x0010` está ensamblada a partir de la celda ABCD, entonces su código máquina ocupa las celdas: ABCD, ABCE, ABCF. Por lo tanto, su ejecución produce las siguientes lecturas:

* Búsqueda de instrucción: ABCD, ABCE, ABCF
* Búsqueda de operandos: BBBB

> Escribir la secuencia de celdas (separadas con ",") que se piden a memoria principal como producto de la ejecución de `SUB R0, [0x9876]`, asumiendo que está ensamblada a partir de la celda 4444. 