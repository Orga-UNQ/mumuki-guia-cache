Durante la ejecución de un programa se accede a memoria con un criterio que **no es al azar**, pero tampoco absolutamente predecible. Los accesos respetan cierta lógica que tiene relación con la naturaleza de la ejecución de los programas, donde se pueden distinguir dos tipos de accesos a memoria:

* por lectura de instrucciones y
* por lectura de datos. 

Es decir, búsqueda de instrucción y búsqueda de operandos, recordando el ciclo de ejecución de instrucción:

![ciclo de ejecución de instrucción](https://raw.githubusercontent.com/Orga-UNQ/mumuki-guia-cache/master/images/ciclo.png)

# Tropezar varias veces con la misma celda
En particular, la ejecución de los programas hace que unas celdas sean mas accedidas que otras, y un motivo de esto es que sean instrucciones que forman parte de una rutina o de una repetición. En estos casos se espera que esas instrucciones sean utilizadas más de una vez. 

> El principio de localidad temporal dice que 
cuando un programa hace referencia a una posición de memoria, esa posición es mas probable de ser necesitada en poco tiempo que otras posiciones.


Por ejemplo, consideremos la siguiente rutina:

```
        MOV R1, 0x0003
arriba: SUB R1, 0x0001
        JNE arriba
```

Si esta rutina está ensamblada a partir de la celda ABC0, entonces su código máquina ocupa las celdas: ABC0, ABC1, ABC2, ABC3, ABC4. 

Al simular su ejecución, se producen la siguiente secuencia de lecturas a memoria principal:

> ABC0,ABC1,ABC2,ABC3,ABC4,ABC2,ABC3,ABC4,ABC2,ABC3,ABC4

Esto muestra que la ejecución de este programa particular hace que algunas celdas sean requeridas mas de una vez.

¿Cuales son esas celdas?
 