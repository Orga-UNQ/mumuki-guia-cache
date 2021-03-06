# Las celdas no vienen solas

Por ejemplo, consideremos el siguiente programa:

```
ADD R0, 0x0010
SUB R0, 0x0099
```
Si este programa está ensamblada a partir de la celda ABC0, entonces su código máquina ocupa las celdas: ABC0, ABC1, ABC2, ABC3. Por lo tanto, su ejecución produce las siguiente secuencia de lecturas a memoria principal:
> ABC0,ABC1,ABC2,ABC3

Y esas lecturas se deben a la **búsqueda de instrucciones**. La lectura de instrucciones es, en su mayoría, un recorrido de celdas consecutivas de memoria. Lo mismo ocurre con la lectura de los datos de un arreglo: lecturas consecutivas de memoria.

Este comportamiento se describe con el nombre de **principio de localidad espacial**. 

> El **principio de localidad espacial** enuncia que *las posiciones de memoria cercanas a alguna accedida recientemente son más probables de ser requeridas que las más distantes*.

Entonces, al observar este programa particular se ve que al requerir una celda (como la ABC0), es mas probable requerir las siguientes celdas (ABC1...) que alguna otra en otro lugar de la memoria.

# A ejercitar

Escribir la secuencia de celdas (separadas con ",") que se piden a memoria principal como producto de la ejecución de `SUB R0, [0x9876]`, asumiendo que está ensamblada a partir de la celda 4444. 