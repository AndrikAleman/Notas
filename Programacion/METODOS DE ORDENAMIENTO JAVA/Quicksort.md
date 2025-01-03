-Es el mas complejo pero el mas eficiente
-Se usan punteros donde se apuntan al principio y ultimo
-Aparte esta el pivote que aquel que se basaran los cambios
![[Pasted image 20250102183452.png]]
1- Se empieza en la derecha (1)
2- Los menores van a la izquierda y los mayores a la derecha dependiendo del puntero
3- pasa al izquierdo (5) y se cambia al derecho 
![[Pasted image 20250102183713.png]]
4- Cuando exista un movimiento de numero la flecha izquierda o derecha se recorrerán uno después o uno antes
5- en este caso el (6) es mayor entonces el derecho se mueve en automático uno antes
![[Pasted image 20250102183851.png]]
6- Cuando la flecha izquierda y derecha lleguen a juntarse será destinado el numero del puntero
![[Pasted image 20250102184014.png]]

Codigo:
1- metodo quicksort principal

```
public void quickSort(int[] arr, int low, int high) {
    if (low < high) {
        int pi = partition(arr, low, high);
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}
```
- Este método recibe tres parámetros:
    - `arr`: el array a ordenar
    - `low`: el índice inicial de la sección a ordenar
    - `high`: el índice final de la sección a ordenar
- La condición `if (low < high)` verifica que haya al menos dos elementos para ordenar
- Llama recursivamente a quickSort en las dos mitades del array (antes y después del pivote)

2- metodo partition
```
private int partition(int[] arr, int low, int high) {
    int pivot = arr[high];    // El pivote es el último elemento
    int i = (low - 1);        // Índice del elemento más pequeño

    for (int j = low; j < high; j++) {
        if (arr[j] < pivot) {
            i++;
            // Intercambio
            int temp = arr[i];
            arr[i] = arr[j];
            arr[j] = temp;
        }
    }
    // Coloca el pivote en su posición correcta
    int temp = arr[i + 1];
    arr[i + 1] = arr[high];
    arr[high] = temp;

    return i + 1;
}
```

Este método es el corazón del algoritmo:

- Selecciona el último elemento como pivote
- `i` mantiene la posición del último elemento menor que el pivote
- El bucle `for` recorre todos los elementos:
    - Si encuentra un elemento menor que el pivote, incrementa `i` y lo intercambia
- Al final, coloca el pivote en su posición correcta (entre los elementos menores y mayores)

3. **Ejemplo de funcionamiento:** Tomemos el array `[64, 34, 25, 12, 22, 11, 90]`:

Primera llamada a partition:

1. Pivote = 90 (último elemento)
2. Después de particionar: `[64, 34, 25, 12, 22, 11] 90`
3. El 90 queda en su posición final

Segunda llamada recursiva (subarray izquierdo):

1. `[64, 34, 25, 12, 22, 11]`
2. Pivote = 11
3. Después de particionar: `[11] [64, 34, 25, 12, 22]`

Y así sucesivamente hasta que todos los elementos están ordenados.

4- Metodo prinarray
```
public void printArray(int[] arr) {
    for (int i : arr) {
        System.out.print(i + " ");
    }
    System.out.println();
}
```
- Es un método auxiliar para imprimir el array
- Usa un bucle for-each para recorrer todos los elementos
- Imprime cada elemento seguido de un espacio

5. **Complejidad del algoritmo:**

- Mejor caso: O(n log n)
- Caso promedio: O(n log n)
- Peor caso: O(n²) - ocurre cuando el array está ya ordenado o inversamente ordenado

6. **Ventajas del Quicksort:**

- Es eficiente en la práctica
- Usa poco espacio adicional (ordena "in-place")
- Funciona bien con la memoria caché
- Se puede optimizar de varias formas (eligiendo mejor el pivote, por ejemplo)

7-Main
```
public static void main(String[] args) {
    int[] arr = {64, 34, 25, 12, 22, 11, 90};
    Quicksort qs = new Quicksort();
    qs.quickSort(arr, 0, arr.length - 1);
}
```
- Crea un array de ejemplo
- Instancia la clase Quicksort
- Llama al método de ordenamiento con el array completo


Codigo completo:
```
public class Quicksort {  
  
    public void quickSort(int[] arr, int low, int high) {  
        if (low < high) {  
            // Encuentra el índice de partición  
            int pi = partition(arr, low, high);  
  
            // Ordena recursivamente los elementos antes y después de la partición  
            quickSort(arr, low, pi - 1);  
            quickSort(arr, pi + 1, high);  
        }  
    }  
  
    private int partition(int[] arr, int low, int high) {  
        // Selecciona el último elemento como pivote  
        int pivot = arr[high];  
  
        // Índice del elemento más pequeño  
        int i = (low - 1);  
  
        for (int j = low; j < high; j++) {  
            // Si el elemento actual es menor que el pivote  
            if (arr[j] < pivot) {  
                i++;  
  
                // Intercambia arr[i] y arr[j]  
                int temp = arr[i];  
                arr[i] = arr[j];  
                arr[j] = temp;  
            }  
        }  
  
        // Intercambia arr[i+1] y arr[high] (el pivote)  
        int temp = arr[i + 1];  
        arr[i + 1] = arr[high];  
        arr[high] = temp;  
  
        return i + 1;  
    }  
  
    // Método auxiliar para imprimir el array  
    public void printArray(int[] arr) {  
        for (int i : arr) {  
            System.out.print(i + " ");  
        }  
        System.out.println();  
    }  
  
    // Método principal para probar el algoritmo  
    public static void main(String[] args) {  
        int[] arr = {64, 34, 25, 12, 22, 11, 90};  
        System.out.println("Array original:");  
  
        Quicksort qs = new Quicksort();  
        qs.printArray(arr);  
  
        qs.quickSort(arr, 0, arr.length - 1);  
  
        System.out.println("Array ordenado:");  
        qs.printArray(arr);  
    }  
}
```

resultado:
```
Array original:
64 34 25 12 22 11 90 
Array ordenado:
11 12 22 25 34 64 90
```
