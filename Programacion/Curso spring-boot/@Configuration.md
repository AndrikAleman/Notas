@Configuracion -> anotación que indica que una clase es una fuente de configuración para el contenedor de spring. Se utilizar principalmente para definir beans que sean gestionado por el contenedor IoC

**Contexto de uso.**
Se utilizar para centralizar la configuración de beans en una clase.

Ejemplo.

```
@Configuration
public class AppConfig {
 
    @Bean
    public MiServicio miServicio() {
        return new MiServicio();
    }
}
```


---
### ¿Qué es @Bean?

Anotación que se utiliza dentro de una clase anotada con @Configuration para definir un bean,  cada método que se registre con esta anotación será registrada en el contenedor de Spring, y el retorno de ese método será inyectado donde sea necesario 


---
### Diferencias entre @Bean y @Component

**@Component (y derivados como @Service, @Repository):** Se utilizan para la autodetección y el escaneo de componentes en el contexto de Spring. Spring detecta automáticamente estos beans durante el escaneo de clases basado en el paquete.

**@Bean:** Se utiliza cuando necesitas más control sobre la creación del bean, como configurar manualmente dependencias, crear instancias condicionalmente o aplicar lógica de inicialización personalizada. **@Bean** no depende del escaneo de componentes y se define explícitamente en una clase **@Configuration**

Ejemplo

```
// Configuración de Beans
@Configuration
public class NotificacionConfig {
 
    @Bean
    public NotificacionCorreo notificacionCorreo() {
        return new NotificacionCorreo();
    }
 
    @Bean
    public NotificacionSMS notificacionSMS() {
        return new NotificacionSMS();
    }
 
    @Bean
    public ServicioNotificacion servicioNotificacion() {
        return new ServicioNotificacion(notificacionCorreo(), notificacionSMS());
    }
}
 
// Implementación de Clases
public class NotificacionCorreo {
    public void enviarCorreo(String mensaje) {
        System.out.println("Enviando correo: " + mensaje);
    }
}
 
public class NotificacionSMS {
    public void enviarSMS(String mensaje) {
        System.out.println("Enviando SMS: " + mensaje);
    }
}
 
public class ServicioNotificacion {
    private final NotificacionCorreo correo;
    private final NotificacionSMS sms;
 
    public ServicioNotificacion(NotificacionCorreo correo, NotificacionSMS sms) {
        this.correo = correo;
        this.sms = sms;
    }
 
    public void notificar(String mensaje) {
        correo.enviarCorreo(mensaje);
        sms.enviarSMS(mensaje);
    }
}
```

