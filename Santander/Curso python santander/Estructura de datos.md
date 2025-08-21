Las estructuras de datos nos permiten organizar y almacenar datos de manera eficiente en nuestros programas. Python proporciona varias estructuras de datos integradas, como listas, tuplas, diccionarios y conjuntos, cada una con sus propias características y usos.

------------

**Listas**
(Se puede modificar los datos)

Una lista es una estructura de datos mutable y ordenada que permite almacenar una colección de elementos. Los elementos de una lista pueden ser de diferentes tipos de datos y se encierran entre corchetes [], separados por comas.

	- Creación y acceso

Para crear una lista, simplemente encierra los elementos entre corchetes:

```
frutas = ["manzana", "banana", "naranja"]
```

Para acceder a los elementos de una lista, utiliza el índice del elemento entre corchetes. Los índices comienzan desde 0.

```
print(frutas[0])  # Imprime "manzana"  
print(frutas[1])  # Imprime "banana"  
print(frutas[2])  # Imprime "naranja"
```

	- Métodos de listas

Las listas en Python tienen varios métodos incorporados que nos permiten manipular y modificar los elementos de la lista. Algunos métodos comunes son:

- **append**(elemento): agrega un elemento al final de la lista.
- **insert**(indice, elemento): inserta un elemento en una posición específica de la lista.
- **remove**(elemento): elimina la primera aparición de un elemento en la lista.
- **pop**(indice): elimina y devuelve el elemento en una posición específica de la lista.
- **sort**(): ordena los elementos de la lista en orden ascendente.
- **reverse()**: invierte el orden de los elementos en la lista.

```
frutas = ["manzana", "banana", "naranja"]  
  
  
frutas.append("pera")  
print(frutas)  # Imprime ["manzana", "banana", "naranja", "pera"]  
  
  
frutas.insert(1, "uva")  
print(frutas)  # Imprime ["manzana", "uva", "banana", "naranja", "pera"]  
  
  
frutas.remove("banana")  
print(frutas)  # Imprime ["manzana", "uva", "naranja", "pera"]  
  
  
fruta_eliminada = frutas.pop(2)  
print(frutas)  # Imprime ["manzana", "uva", "pera"]  
print(fruta_eliminada)  # Imprime "naranja"  
  
  
frutas.sort()  
print(frutas)  # Imprime ["manzana", "pera", "uva"]  
  
  
frutas.reverse()  
print(frutas)  # Imprime ["uva", "pera", "manzana"]
```



-----------------
**Tuplas**

Una tupla es una estructura de datos inmutable y ordenada que permite almacenar una colección de elementos. Los elementos de una tupla se encierran entre paréntesis (), separados por comas.

- Creación y acceso

Para crear una tupla, encierra los elementos entre paréntesis:

```
punto = (3, 4)

print(punto[0])  # Imprime 3  
  
print(punto[1])  # Imprime 4
```

A diferencia de las listas, las tuplas son inmutables, lo que significa que no se pueden modificar una vez creadas. No se pueden agregar, eliminar o cambiar elementos en una tupla existente.

- Métodos de tuplas

Aunque las tuplas son inmutables, Python proporciona varios métodos útiles para trabajar con ellas:

- **count(elemento):** devuelve el número de veces que aparece un elemento en la tupla. 
- **index(elemento):** devuelve el índice de la primera aparición de un elemento en la tupla. Opcionalmente, se puede especificar el inicio y fin de la búsqueda. 
- **len(tupla):** aunque no es un método de tupla propiamente dicho, esta función incorporada devuelve la longitud de la tupla.

```
mi_tupla = (1, 2, 3, 2, 4, 2)  
  
  
print (mi_tupla.index(2))   # Salida: 1  
  
print (mi_tupla.index(2, 2))   #Salida: 3  
  
print (mi_tupla.index(2, 2, 4))   #Salida: 3
```


----------------------
**Diccionarios**

Un diccionario es una estructura de datos mutable y no ordenada que permite almacenar pares de clave-valor. Cada elemento en un diccionario consiste en una clave única y su valor correspondiente. Los diccionarios se encierran entre llaves {}, y los pares clave-valor se separan por comas.

- Creación y acceso

Para crear un diccionario, utiliza llaves y separa las claves y valores con dos puntos.

```
persona = {"nombre": "Juan", "edad": 25, "ciudad": "Madrid"}
```

Para acceder a los valores de un diccionario, utiliza la clave correspondiente entre corchetes:

```
print(persona["nombre"])  # Imprime "Juan"  
print(persona["edad"])    # Imprime 25  
print(persona["ciudad"])  # Imprime "Madrid"
```

- Métodos de diccionarios

Los diccionarios en Python tienen varios métodos incorporados para manipular y acceder a los elementos. Algunos métodos comunes son:

- **keys():** devuelve una vista de todas las claves del diccionario.
- **values():** devuelve una vista de todos los valores del diccionario.
- **items():** devuelve una vista de todos los pares clave-valor del diccionario.
- **update(otro_diccionario):** actualiza el diccionario con los pares clave-valor de otro diccionario.

```
persona = {"nombre": "Juan", "edad": 25, "ciudad": "Madrid"}  
  
  
print(persona.keys())    # Imprime dict_keys(["nombre", "edad", "ciudad"])  
print(persona.values())  # Imprime dict_values(["Juan", 25, "Madrid"])  
print(persona.items())   # Imprime dict_items([("nombre", "Juan"), ("edad", 25), ("ciudad", "Madrid")])  
  
  
persona.update({"profesion": "Ingeniero"})  
print(persona)  # Imprime {"nombre": "Juan", "edad": 25, "ciudad": "Madrid", "profesion": "Ingeniero"}
```


------------
**Conjuntos**
Un conjunto es una estructura de datos mutable y no ordenada que permite almacenar una colección de elementos únicos. Los conjuntos se encierran entre llaves {} o se crean utilizando la función set().


- Creación y operaciones básicas

Para crear un conjunto, utiliza llaves o la función set():

```
frutas = {"manzana", "banana", "naranja"}  
numeros = set([1, 2, 3, 4, 5])
```

Los conjuntos admiten operaciones matemáticas de conjuntos, como la unión (|), la intersección (&), la diferencia (-) y la diferencia simétrica (^).

```
conjunto1 = {1, 2, 3}  
conjunto2 = {3, 4, 5}  
  
  
union = conjunto1 | conjunto2  
print(union)  # Imprime {1, 2, 3, 4, 5}  
  
  
interseccion = conjunto1 & conjunto2  
print(interseccion)  # Imprime {3}  
  
  
diferencia = conjunto1 - conjunto2  
print(diferencia)  # Imprime {1, 2}  
  
  
diferencia_simetrica = conjunto1 ^ conjunto2  
print(diferencia_simetrica)  # Imprime {1, 2, 4, 5}
```

- Métodos de conjuntos

Los conjuntos en Python tienen varios métodos incorporados para manipular y acceder a los elementos. Algunos métodos comunes son:

- add(elemento): agrega un elemento al conjunto.
- remove(elemento): elimina un elemento del conjunto. Si el elemento no existe, genera un error.
- discard(elemento): elimina un elemento del conjunto si está presente. Si el elemento no existe, no hace nada.
- clear(): elimina todos los elementos del conjunto.

```
frutas = {"manzana", "banana", "naranja"}  
  
  
frutas.add("pera")  
print(frutas)  # Imprime {"manzana", "banana", "naranja", "pera"}  
  
  
frutas.remove("banana")  
print(frutas)  # Imprime {"manzana", "naranja", "pera"}  
  
  
frutas.discard("uva")  
print(frutas)  # Imprime {"manzana", "naranja", "pera"}  
  
  
frutas.clear()  
print(frutas)  # Imprime set()
```

