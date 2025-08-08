En Python, la entrada y salida de datos nos permite interactuar con el usuario y manipular archivos. Podemos solicitar información al usuario, mostrar resultados en la pantalla y leer o escribir datos en archivos externos.

## **Entrada de datos del usuario**

Para obtener información del usuario durante la ejecución del programa, podemos utilizar la función input(). Esta función muestra un mensaje en la pantalla y espera a que el usuario ingrese un valor.
```
nombre = input("Ingresa tu nombre: ")  
edad = input("Ingresa tu edad: ")  
  
  
print("Hola, " + nombre + "!")  
print("Tienes " + edad + " años.")
```

## **Salida de datos**

Para mostrar información en la pantalla, utilizamos la función print(). Esta función toma uno o más argumentos y los muestra en la consola.

Podemos utilizar la f-string (formateo de cadenas) para incrustar variables directamente dentro de una cadena de texto.

```
nombre = "Juan"  
edad = 25  
  
  
print(f"Hola, mi nombre es {nombre} y tengo {edad} años.")
```

