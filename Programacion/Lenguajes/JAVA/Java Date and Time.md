- La [Clase de calendario](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html) es una clase abstracta que proporciona métodos para convertir entre un instante específico en el tiempo y un conjunto de campos de calendario como AÑO, MES, DAY_OF_MONTH, HORA, etc., y para manipular los campos del calendario, como obtener la fecha de la semana siguiente.

![[Pasted image 20241207200357.png]]

```
class Result {
    /*

     * Complete the 'findDay' function below.

     *

     * The function is expected to return a STRING.

     * The function accepts following parameters:

     *  1. INTEGER month

     *  2. INTEGER day

     *  3. INTEGER year

     */

    public static String findDay (int month, int day, int year) {

        Calendar cale = Calendar.getInstance();

        cale.set(Calendar.MONTH, month-1);

        cale.set(Calendar.DATE, day);

        cale.set(Calendar.YEAR, year);

        String dayofweek = cale.getDisplayName(Calendar.DAY_OF_WEEK, Calendar.LONG, Locale.US).toUpperCase();

        return dayofweek;
    }
}
```

- Uso Calendar y obtengo la instancia, con las variables mes, dia y año, lo obtengo con calendar y asigno a las variables.


```
public class Solution {

    public static void main(String[] args) throws IOException {

        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));

        BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(System.getenv("OUTPUT_PATH")));

  
        String[] firstMultipleInput = bufferedReader.readLine().replaceAll("\\s+$", "").split(" ");

        int month = Integer.parseInt(firstMultipleInput[0]);

        int day = Integer.parseInt(firstMultipleInput[1]);

        int year = Integer.parseInt(firstMultipleInput[2]);

        String res = Result.findDay(month, day, year);

        bufferedWriter.write(res);

        bufferedWriter.newLine();

        bufferedReader.close();

        bufferedWriter.close();
    }
}
```