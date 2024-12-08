-  Para ver que tipo de dato es dependiendo de los bytes que ocupe
- Ayuda en la optimización de código por el uso de memoria

```
public class JavaDatatypes {  
    public static void main(String[] args) {  
  
        Scanner sc = new Scanner(System.in);  
        int t=sc.nextInt();  
  
        for(int i=0;i<t;i++)  
        {  
  
            try  
            {  
                long x=sc.nextLong();  
                System.out.println(x+" can be fitted in:");  
                if(x>=-128 && x<=127)System.out.println("* byte");  
                if(x>=-32768 && x<=32767){  
                    System.out.println("* short");  
                }  
                if(x>=-Math.pow(2,31) && x<=Math.pow(2,31) -1 ){  
                    System.out.println("* int");  
                }  
                if(x>=-Math.pow(2,63) && x<=Math.pow(2,63) -1 ){  
                    System.out.println("* long");  
                }  
                //Complete the code  
            }  
            catch(Exception e)  
            {  
                System.out.println(sc.next()+" can't be fitted anywhere.");  
            }  
  
        }  
    }  
}
```
----------------------------------------------------
- Si es de -128 a 127 es  => byte
- Si es de -32768 a 32767 es  => short
- Si es de -2^31 a 2^31 es  => int
- Si es de -2^63 a 2^63 es  => long