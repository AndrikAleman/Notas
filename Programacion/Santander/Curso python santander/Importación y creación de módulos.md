En Python, un módulo es un archivo que contiene definiciones de funciones, clases y variables que se pueden utilizar en otros programas. La importación de módulos nos permite acceder a la funcionalidad definida en otros archivos y reutilizar código de manera eficiente. Además, podemos crear nuestros propios módulos para organizar y modularizar nuestro código

## **Importar módulos**

Para utilizar un módulo en nuestro programa, debemos importarlo utilizando la declaración import. Podemos importar un módulo completo o funciones específicas de un módulo.

```
import math  
  
  
resultado = math.sqrt(25)  
print(resultado)  # Imprime 5.0
```

También podemos importar funciones específicas de un módulo utilizando la sintaxis from módulo import función.

```
from math import sqrt  
  
  
resultado = sqrt(25)  
print(resultado)  # Imprime 5.0
```

