## **1. Fundamentos de Java y POO**

**1.1** ¿Qué es Java y sus características?  
➡ Lenguaje orientado a objetos, multiplataforma, seguro, robusto, con manejo automático de memoria (Garbage Collector) y portabilidad gracias a la JVM.

**1.2** Clase vs Objeto  
➡ Clase: plantilla o molde. Objeto: instancia de una clase con datos y comportamiento propios.

**1.3** Herencia  
➡ Permite que una clase hija adquiera atributos y métodos de una clase padre (`extends`).

**1.4** Clase abstracta vs Interface  
➡ Abstracta: puede tener métodos con implementación y abstractos, se hereda con `extends`.  
➡ Interface: solo métodos abstractos (Java 8 permite `default` y `static`), se implementa con `implements`.

**1.5** Overloading vs Overriding  
➡ Overloading: mismo nombre, distinta firma de parámetros.  
➡ Overriding: misma firma, distinta implementación en subclase.

**1.6** Polimorfismo  
➡ Capacidad de un objeto para comportarse de distintas formas según el contexto.

**1.7** Modificadores de acceso  
➡ `public`: accesible desde cualquier clase.  
➡ `private`: solo en la misma clase.  
➡ `protected`: misma clase, subclases y mismo paquete.  
➡ _default_: solo en el mismo paquete.

**1.8** Tipos primitivos vs objetos  
➡ Primitivos: almacenan valores directos (`int`, `double`).  
➡ Objetos: referencias a instancias (`String`, `Integer`).

**1.9** Encapsulamiento  
➡ Ocultar detalles internos de una clase y exponer solo lo necesario mediante getters/setters.

**1.10** Constructor  
➡ Método especial para inicializar objetos, se ejecuta al crear la instancia.

---

## **2. Conceptos clave de Java**

**2.1** `final` vs `finally` vs `finalize()`  
➡ `final`: constante o clase/método no modificable.  
➡ `finally`: bloque que siempre se ejecuta después de `try-catch`.  
➡ `finalize()`: método llamado por el GC antes de destruir un objeto (en desuso).

**2.2** Variables locales, de instancia y estáticas  
➡ Locales: dentro de un método.  
➡ De instancia: pertenecen al objeto.  
➡ Estáticas: compartidas entre todas las instancias.

**2.3** Bloque `static`  
➡ Código que se ejecuta una sola vez al cargar la clase.

**2.4** `String` vs `StringBuilder` vs `StringBuffer`  
➡ `String`: inmutable.  
➡ `StringBuilder`: mutable, no sincronizado.  
➡ `StringBuffer`: mutable, sincronizado.

**2.5** Inmutabilidad de `String`  
➡ Mejora seguridad, cacheo y optimización en el _String Pool_.

**2.6** Boxing y Unboxing  
➡ Boxing: convertir primitivo en objeto (`int` → `Integer`).  
➡ Unboxing: convertir objeto a primitivo (`Integer` → `int`).

**2.7** Wrapper classes  
➡ Clases que envuelven tipos primitivos (`Integer`, `Double`).

**2.8** Enumeraciones (`enum`)  
➡ Tipo especial con valores fijos predefinidos.

---

## **3. Colecciones**

**3.1** List vs Set vs Map  
➡ List: ordenada, permite duplicados.  
➡ Set: no permite duplicados.  
➡ Map: pares clave-valor, claves únicas.

**3.2** ArrayList vs LinkedList  
➡ ArrayList: acceso rápido, inserción lenta.  
➡ LinkedList: acceso lento, inserción rápida.

**3.3** HashMap  
➡ Basado en hash, clave-valor, acceso rápido.

**3.4** TreeMap  
➡ Ordena por clave de forma natural.

**3.5** Comparable vs Comparator  
➡ Comparable: define orden natural en la clase (`compareTo`).  
➡ Comparator: define orden externo (`compare`).

**3.6** Iterator  
➡ Recorre colecciones secuencialmente.

**3.7** Fail-fast vs Fail-safe  
➡ Fail-fast: lanza excepción si se modifica al iterar (`ArrayList`).  
➡ Fail-safe: permite cambios (`CopyOnWriteArrayList`).

---

## **4. Excepciones**

**4.1** Checked vs Unchecked  
➡ Checked: deben manejarse o declararse (`IOException`).  
➡ Unchecked: tiempo de ejecución (`NullPointerException`).

**4.2** Error vs Exception  
➡ Error: problemas graves no recuperables.  
➡ Exception: errores que pueden manejarse.

**4.3** throw vs throws  
➡ `throw`: lanza una excepción.  
➡ `throws`: declara excepciones que puede lanzar un método.

**4.4** Excepción personalizada  
➡ Clase que extiende `Exception` o `RuntimeException`.

**4.5** try-with-resources  
➡ Maneja recursos automáticamente (`AutoCloseable`).

---

## **5. OOP Avanzado**

**5.1** Composición vs Herencia  
➡ Composición: un objeto contiene otros objetos.  
➡ Herencia: relación padre-hijo.

**5.2** Método `static`  
➡ Pertenece a la clase, no a la instancia.

**5.3** Clases internas  
➡ Clases dentro de otras (`inner`, `static nested`, `local`, `anonymous`).

**5.4** Upcasting y Downcasting  
➡ Upcasting: subclase a superclase (seguro).  
➡ Downcasting: superclase a subclase (requiere conversión explícita).

**5.5** `super`  
➡ Llama al constructor o métodos de la clase padre.

---

## **6. Java Moderno**

**6.1** Switch Expressions (Java 14+)  
➡ Sintaxis mejorada con `->` y `yield`.

**6.2** Record  
➡ Clase inmutable para almacenar datos (`record User(String name, int age) {}`).

**6.3** Sealed classes  
➡ Restringen qué clases pueden heredar.

**6.4** API `java.time`  
➡ Manejo de fechas/horas con `LocalDate`, `LocalTime`, `LocalDateTime`.

**6.5** `var`  
➡ Inferencia de tipo en variables locales.

---

## **7. Concurrencia**

**7.1** Thread vs Runnable  
➡ Thread: clase para crear hilos.  
➡ Runnable: interfaz para definir tarea en un hilo.

**7.2** `synchronized`  
➡ Evita que varios hilos modifiquen un recurso a la vez.

**7.3** ExecutorService  
➡ Gestiona un pool de hilos.

**7.4** Race condition  
➡ Error por acceso concurrente sin control.

---

## **9. Base de Datos**

**9.1** JPA vs Hibernate  
➡ JPA: especificación. Hibernate: implementación.

**9.2** JPQL  
➡ Consultas orientadas a objetos.

**9.3** @Query  
➡ Define consulta personalizada en repositorio.

**9.4** Transaction  
➡ Bloque atómico de operaciones (`@Transactional`).

**9.5** INNER JOIN vs LEFT JOIN  
➡ INNER JOIN: solo registros que cumplen en ambas tablas.  
➡ LEFT JOIN: todos los de la izquierda y coincidencias de la derecha.

----
### JVM (Java Virtual Machine)**

- Es la **máquina virtual** que ejecuta el código Java.
    
- Traduce el **bytecode** (archivo `.class`) a instrucciones entendibles por el sistema operativo.
    
- Hace que Java sea **multiplataforma** (_Write Once, Run Anywhere_).
    
- La JVM no compila tu código, solo lo ejecuta.
    

---

### JRE (Java Runtime Environment)**

- Es el **entorno de ejecución** de Java.
    
- Incluye:
    
    - **JVM**
        
    - Librerías estándar (API de Java)
        
- Sirve **solo para ejecutar** programas Java, no para desarrollarlos.
    
- Ejemplo: un usuario que solo quiere correr tu app necesita el **JRE**.
    

---

## **JDK (Java Development Kit)**

- Es el **kit de desarrollo** para programar en Java.
    
- Incluye:
    
    - **JRE**
        
    - Herramientas de desarrollo (`javac`, `java`, `javadoc`, depuradores, etc.)
        
- Si vas a **programar**, necesitas el JDK.
    
- Si solo quieres **ejecutar**, basta el JRE.

------------------

¿Cuál es el alcance de acceso del especificador de acceso protegido?

Cuando un método o una variable se declara con el especificador de acceso protegido, se vuelve accesible en la misma clase, en cualquier otra clase del mismo paquete y en una subclase.

|Cambiar|Clase|PREMIUM|Subclase|Mundo|
|---|---|---|---|---|
|público|Y|Y|Y|Y|
|protegido|Y|Y|Y|N|
|sin modificador|Y|Y|N|N|
|privada|Y|N|N|N|

### ¿Cuál es la diferencia entre pila y cola?

Tanto la pila como la cola se utilizan como marcador de posición para una colección de datos. La principal diferencia entre una pila y una cola es que la pila se basa en el principio de último en entrar, primero en salir (LIFO), mientras que una cola se basa en el principio FIFO (primero en entrar, primero en salir).

