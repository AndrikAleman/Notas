- Escribe un programa que imprima los 50 primeros números de la sucesión 
- de Fibonacci empezando en 0.
- La serie Fibonacci se compone por una sucesión de números en
- la que el siguiente siempre es la suma de los dos anteriores.
- 0, 1, 1, 2, 3, 5, 8, 13... 

```
public void fibo(){  
    int n1 = 0;  
    int n2 = 1;  
  
    for(int i=0; i<=50; i++){  
        System.out.println(n1);  
  
        int var = n1 + n2;  
        n1 = n2;  
        n2 = var;  
    }  
}
```

-------------------------------------------------------
- Se crean las variables
- Se crea la variable 1 para que empiece la suma
- Empieza el loop
- Se imprime 0
- Se crea la variable var = 0 + 1;
- a n1 = 1
- a n2 = var(1)
- Se imprime 1

Al final se crean 50 numeros de fibonacci.
