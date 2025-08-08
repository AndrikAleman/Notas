Anotacion que combina las funcionalidades de @Controller y @ResponseBody, Se utiliza para gestionar solicitudes HTTP y devuelven (Datos en formato JSON o XML)

- @Controller: Indica que una clase es un controlador
- @ResponseBody: Indica que el retorno de los métodos se serializa directamente al cuerpo de la respuesta (En lugar de devolver una vista)

En resumen, **@RestController** simplifica la creación de APIs RESTful al evitar la necesidad de usar **@ResponseBody** en cada método.

Ejemplo:
```
@RestController
public class SaludoController {
 
    @GetMapping("/saludo")
    public String saludar() {
        return "¡Hola, bienvenido a Spring Boot!";
    }
}
```

