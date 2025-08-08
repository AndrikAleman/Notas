Python fue creado por Guido van Rossum


--------------------------

**¿Qué son las variables?**
Las variables son contenedores que nos permiten almacenar y manipular datos en nuestros programas

![[Pasted image 20250424122654.png]]

---------------------

**Operadores logicos**

![[Pasted image 20250424122850.png]]


------------------------

**Bucles / Loops**

**For** -> Debes de conocer cuantas veces se ejecutara
El bucle for se utiliza para iterar sobre una secuencia (como una lista, una tupla o una cadena) o cualquier objeto iterable. La sintaxis básica es la siguiente:

```
for variable in secuencia:  
  
    # Bloque de código a repetir  
    instrucciones
```

Ejemplo:
```
frutas = ["manzana", "banana", "naranja"]  
  
  
for fruta in frutas:  
    print(fruta)
```


**while** -> Se ejecuta mientras haya una condicion que cumplir
El bucle while se utiliza para repetir un bloque de código mientras una condición sea verdadera. La sintaxis básica es la siguiente:

```
while condicion:  
  
    # Bloque de código a repetir  
    instrucciones
```

Ejemplo:
```
contador = 0  
  
  
while contador < 5:  
  
    print(contador)  
    contador += 1
```

-------------------
**Controles de bucles**

Python tiene instrucciones especiales para controlar el flujo de ejecuciones dentro de los bucles.

**Break**

La instrucción break se utiliza para salir prematuramente de un bucle, independientemente de la condición. Cuando se encuentra un break, el bucle se detiene y el flujo de ejecución continúa con la siguiente instrucción fuera del bucle.

```
contador = 0  
  
  
while True:  
  
    print(contador)  
    contador += 1  
  
  
    if contador == 5:  
        break
```


**Continue**
La instrucción continue se utiliza para saltar el resto del bloque de código dentro de un bucle y pasar a la siguiente iteración.

```
for i in range(10):  
  
    if i % 2 == 0:  
        continue  
    print(i)
```

En este ejemplo, el bucle for itera sobre los números del 0 al 9 utilizando la función range(). Dentro del bucle, se verifica si el número es divisible por 2 utilizando el operador de módulo %. Si el número es divisible por 2 (es decir, si es par), se ejecuta la instrucción continue, lo que hace que se salte el resto del bloque de código y se pase a la siguiente iteración del bucle. Como resultado, solo se imprimirán los números impares.