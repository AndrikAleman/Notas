### @Controller: Manejo de solicitudes Web

@Controller -> Especializacion de @Component diseñada para maenrjas solicitudes web (HTTP) y devolver vistas o datos. En la arquitectura **MVC (Model-View-Controller)**, un @Controller actua como intermediario entre el modelo y la vista.

**Uso común**: En aplicaciones web para manejar solicitudes HTTP y devolver respuestas, ya sea en formato HTML (en aplicaciones web tradicionales) o JSON (en APIs REST).

En aplicaciones RESTful, se suele usar **@RestController**, que es una combinación de **@Controller** y **@ResponseBody**, para retornar datos JSON en lugar de vistas.

```
@Controller
public class MiControlador {
 
    @GetMapping("/saludo")
    public String mostrarSaludo(Model model) {
        model.addAttribute("mensaje", "Hola desde Spring Boot!");
        return "saludo"; // Retorna una vista llamada "saludo.html"
    }
}
```
