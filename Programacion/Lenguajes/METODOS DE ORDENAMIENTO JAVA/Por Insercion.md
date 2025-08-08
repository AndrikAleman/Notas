-Manera natural de ordenar para un ser humano.
-Requiere O(n)^2 operaciones para ordenar una lista de n elementos

![[Pasted image 20250102180959.png]]
Pasos:
(Si nIzquierda > nActual) --> cambia

1- 5 comprueba que a la izquierda del 5 es mayor--> no, pasa al otro
2- 3 comprueba si el numero 5 es mayor --> si cambia
3- verifica 3 si hay otro mas grande a la izquierda --> no , pasa al otro
![[Pasted image 20250102181317.png]]
4- 4 es mayor a 5 --> si cambia

Codigo:

```
public class Insercion {  
    Scanner teclado = new Scanner(System.in);  
  
  
    public static void main(String[] args) {  
        int arreglo[], nElementos,nums, flag, aux;  
  
        nElementos = Integer.parseInt(JOptionPane.showInputDialog("Ingresa la cantidad de numeros a ingresar: "));  
        arreglo = new int[nElementos];  
  
        for (int i = 0; i < nElementos; i++) {  
            nums = Integer.parseInt(JOptionPane.showInputDialog("Ingrese el numero del elemento " + i + ": "));  
            arreglo[i] = nums;  
        }  
  
        for (int i = 0; i < nElementos; i++) {  
            //flag es la posicion del elemento que vera  
            flag = i;  
            //aux es el valor del elemento de esa flag  
            aux = arreglo[i];  
  
            //Para hacer las comprobaciones del lado izquierdo  
            //flag es para que inicie con el primer elemento y los demas lleguen hasta ese            //and            //comprobar que el numero de la izquierda es mayor al actual            while ((flag > 0) && (arreglo[flag - 1] > aux)) {  
                arreglo[flag] = arreglo[flag - 1];  
                flag--;  
            }  
  
            //Para refrescar  
            arreglo[flag] = aux;  
  
        }  
  
  
  
        System.out.println("Este arreglo esta en forma creciente");  
        for (int i = 0; i < nElementos; i++) {  
            System.out.print(arreglo[i] + " ");  
        }  
    }  
  
}
```