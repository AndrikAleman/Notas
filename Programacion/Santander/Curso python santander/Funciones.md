
Las funciones son bloques de código reutilizables que nos permiten encapsular tareas específicas y ejecutarlas cuando sea necesario. Las funciones nos ayudan a organizar nuestro código, evitar la repetición y hacer que nuestros programas sean más modulares y fáciles de mantener



## **Definición y llamada de funciones**

Para definir una función en Python, utilizamos la palabra clave def seguida del nombre de la función y paréntesis. Opcionalmente, podemos especificar parámetros dentro de los paréntesis. El bloque de código de la función se indenta después de los dos puntos.

```
def saludo():  
    print("¡Hola, mundo!")  
  
  
saludo()  # Imprime "¡Hola, mundo!"
```

## **Parámetros y argumentos**

Las funciones pueden aceptar parámetros, que son valores que se pasan a la función cuando se la llama. Los parámetros se especifican dentro de los paréntesis en la definición de la función.

```
def saludo(nombre):  
    print(f"¡Hola, {nombre}!")
```

Al llamar a la función, proporcionamos los argumentos correspondientes a los parámetros:

```
saludo("Juan")  # Imprime "¡Hola, Juan!"  
saludo("María")  # Imprime "¡Hola, María!"
```

## **Valores de retorno**

Las funciones pueden devolver valores utilizando la palabra clave return. El valor de retorno puede ser utilizado por el código que llama a la función.

```
def suma(a, b):  
    return a + b  
  
  
resultado = suma(3, 4)  
print(resultado)  # Imprime 7
```

## **Funciones anónimas (lambda)**

Python permite crear funciones anónimas o funciones lambda, que son funciones sin nombre definidas en una sola línea. Se utilizan comúnmente para funciones pequeñas y concisas.

```
cuadrado = lambda x: x ** 2  
print(cuadrado(5))  # Imprime 25
```


## **Alcance de las variables (local vs. global)**

Las variables definidas dentro de una función tienen un alcance local, lo que significa que solo son accesibles dentro de la función. Por otro lado, las variables definidas fuera de cualquier función tienen un alcance global y pueden ser accedidas desde cualquier parte del programa.

```
def funcion():  
    variable_local = 10  
    print(variable_local)  # Accesible dentro de la función  
  
  
variable_global = 20  
  
  
def funcion2():  
    print(variable_global)  # Accesible desde cualquier lugar  
  
  
funcion()  # Imprime 10  
funcion2()  # Imprime 20  
print(variable_global)  # Imprime 20  
print(variable_local)  # Genera un error, la variable no está definida en este alcance.
```

- Documentación de funciones (docstrings)
Es una buena práctica documentar nuestras funciones utilizando docstrings. Los docstrings son cadenas de texto que describen el propósito, los parámetros y el valor de retorno de una función. Se colocan inmediatamente después de la definición de la función y se encierran entre triples comillas dobles.

```
def area_rectangulo(base, altura):  
    """  
    Calcula el área de un rectángulo.  
  
  
    Args:  
        base (float): La base del rectángulo.  
        altura (float): La altura del rectángulo.  
  
  
    Returns:  
        float: El área del rectángulo.  
    """  
    return base * altura
    
```


- Funciones con número variable de argumentos

Python permite definir funciones que acepten un número variable de argumentos. Esto se logra utilizando el operador * antes del nombre del parámetro.

```
def suma_variable(*numeros):  
    total = 0  
    for numero in numeros:  
        total += numero  
    return total  
  
  
print(suma_variable(1, 2, 3))  # Imprime 6  
print(suma_variable(4, 5, 6, 7))  # Imprime 22
```

