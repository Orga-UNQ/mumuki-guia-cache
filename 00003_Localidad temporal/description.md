Durante la ejecución de un programa se accede a memoria con un criterio que no es al azar, pero tampoco absolutamente predecible. Los accesos respetan cierta lógica que tiene relación con la naturaleza de la ejecución de los programas, donde se pueden distinguir dos tipos de accesos a memoria:

* por lectura de instrucciones y
* por lectura de datos. 



Por otro lado, las instrucciones de una rutina o de una repetición se espera que sean utilizadas más de una vez.


El principio de localidad temporal dice que cuando un programa hace referencia a una posición de memoria que contiene una instrucción, es probable que lo vuelva a hacer en poco tiempo.


Por ejemplo, consideremos la siguiente rutina:

```
        MOV R1, 0x0003
arriba: SUB R1, 0x0001
        JNE arriba
```

Si esta rutina está ensamblada a partir de la celda ABC0, entonces su código máquina ocupa las celdas: ABC0, ABC1, ABC2, ABC3, ABC4. 

Al simular su ejecución, se producen la siguiente secuencia de lecturas a memoria principal:

> ABC0,ABC1,ABC2,ABC3,ABC4,ABC2,ABC3,ABC4,ABC2,ABC3,ABC4

Esto muestra que la ejecución de este programa particular hace que algunas celdas sean requeridas mas de una vez: ABC2,ABC3,ABC4
 