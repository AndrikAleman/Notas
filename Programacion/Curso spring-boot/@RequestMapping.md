Se utiliza para mapear solicitudes HTTP a clases o métodos específicos en un controlador. Es una anotación muy flexible que permite especificar.

- La ruta de la solicitud.
- El método HTTP (GET, POST, PUT, DELETE, etc.).
- Parámetros, cabeceras, tipos de contenido, y más.

**@RequestMapping** se puede aplicar a nivel de clase y método:

**A nivel de clase:** Define una ruta base para todas las solicitudes dentro del controlador.

**A nivel de método:** Define rutas específicas para cada método, opcionalmente sobre la ruta base.

Ejemplo:
```
@RestController
@RequestMapping("/usuarios")
public class UsuarioController {
 
    @GetMapping
    public List<String> obtenerUsuarios() {
        return new Usuario("Usuario1");
    }
}
```

Explicación.
En este ejemplo:

- **@RequestMapping(“/usuarios”)**: Define la ruta base para todas las solicitudes de este controlador.
- **@GetMapping**: Mapea la ruta `/usuarios` al método `obtenerUsuarios()`.

---

#### **¿Qué es @GetMapping?**

**@GetMapping** es una anotación específica para manejar solicitudes HTTP GET. Es un atajo de **@RequestMapping(method = RequestMethod.GET)**. Se utiliza cuando deseas que un método responda a solicitudes GET, las cuales generalmente se usan para leer datos o recuperar recursos.