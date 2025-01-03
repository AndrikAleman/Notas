-Revisa cada una con el otro, uno por uno con el otro e intercambia la posición, se hace las veces que sea necesario ( No es muy eficiente)
-Usando JOptionPane

![[Pasted image 20241227141711.png]]

Ejemplo.

4,5,2,1,3    -->  4,2,5,1,3  --> 4,2,1,5,3  -- > 4,2,1,3,5  así sucesivamente.

Código.
```
public class burbuja {  
    //Para el ordenamiento de un array unidimensional  
    //Metodo de la burbuja  
    public static void main(String[] args) {  
        Scanner entrada = new Scanner(System.in);  
        int arreglo[], nElementos, aux, nums;  
  
        nElementos = Integer.parseInt(JOptionPane.showInputDialog("Ingresa la cantidad de numeros a ingresar: "));  
        arreglo = new int[nElementos];  
  
        for (int i = 0; i < nElementos; i++) {  
            nums = Integer.parseInt(JOptionPane.showInputDialog("Ingrese el numero del elemento " + i + ": "));  
            arreglo[i] = nums;  
        }  
  
        //Metodo de burbuja  
        for ( int x = 0; x < (nElementos - 1); x++) {  
            for ( int y = 0; y < (nElementos - 1); y++) {  
                if (arreglo[y] > arreglo[y+1]){  
                    aux = arreglo[y];  
                    arreglo[y] = arreglo[y+1];  
                    arreglo[y+1] = aux;  
                    //Si NActual > Nsiguiente  
                }  
            }  
        }  
  
  
        System.out.println("Este arreglo esta en forma creciente");  
        for (int i = 0; i < nElementos; i++) {  
            System.out.print(arreglo[i] + " ");  
        }  
  
        System.out.println(" ");  
        System.out.println("Este arreglo esta en forma decreciente");  
        for (int i = (nElementos-1); i >= 0; i--) {  
            System.out.print(arreglo[i] + " ");  
        }  
    }  
}
```

-Primer "for" sirve para saber cuantas vueltas tiene que dar 
-El segundo "for anidado" para ordenar los numeros