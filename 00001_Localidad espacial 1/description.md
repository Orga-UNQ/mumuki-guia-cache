# Accesos a memoria principal

Durante la ejecución de un programa se accede a memoria con un criterio que no es aleatorio, pero tampoco absolutamente predecible. Los accesos respetan cierta lógica que tiene relación con la naturaleza de la **ejecución de los programas**, donde se pueden distinguir dos tipos de accesos a memoria: 
* por lectura de instrucciones y 
* por lectura de datos.


Por ejemplo, consideremos el siguiente programa:

```
ADD R0, 0x0010
SUB R0, 0x0099
```
Si este programa está ensamblada a partir de la celda ABC0, entonces su código máquina ocupa las celdas: ABC0, ABC1, ABC2, ABC3. Por lo tanto, su ejecución produce las siguiente secuencia de lecturas a memoria principal:
> ABC0,ABC1,ABC2,ABC3

La lectura de instrucciones es, en su mayoría, un recorrido de celdas consecutivas de memoria. Lo mismo ocurre con la lectura de los datos de un arreglo: lecturas consecutivas de memoria.

Este comportamiento se describen con el nombre de **principio de localidad espacial**. Este principio enuncia que *las posiciones de memoria cercanas a alguna accedida recientemente son más probables de ser requeridas que las más distantes*. 


> Escribir la secuencia de celdas (separadas con ",") que se piden a memoria principal como producto de la ejecución de `SUB R0, [0x9876]`, asumiendo que está ensamblada a partir de la celda 4444. 