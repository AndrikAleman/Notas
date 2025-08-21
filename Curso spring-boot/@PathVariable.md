Se utiliza para extraer valores dinámicos de la URL y pasarlos como argumentos a los métodos del controlador. Es útil para identificar un recurso en especifico.

Por ejemplo, en una URL como `/api/usuarios/1`, el `1` es un ID dinámico que puede ser capturado con **@PathVariable** para buscar un usuario específico en una lista.

Ahora, crearemos un controlador REST que maneje solicitudes para devolver un usuario específico según su ID.

```
@RestController
@RequestMapping("/api/usuarios")
public class UsuarioController {
 
    private List<Usuario> usuarios = new ArrayList<>(List.of(
        new Usuario(1L, "Juan Pérez", "juan.perez@example.com"),
        new Usuario(2L, "María López", "maria.lopez@example.com"),
        new Usuario(3L, "Carlos Sánchez", "carlos.sanchez@example.com")
    ));
 
    // Obtener todos los usuarios
    @GetMapping
    public List<Usuario> obtenerTodosLosUsuarios() {
        return usuarios;
    }
 
    // Obtener un usuario por su ID
    @GetMapping("/{id}")
    public ResponseEntity<Usuario> obtenerUsuarioPorId(@PathVariable Long id) {
        return usuarios.stream()
                .filter(usuario -> usuario.getId().equals(id))
                .findFirst()
                .map(ResponseEntity::ok)
                .orElse(ResponseEntity.notFound().build());
    }
}
```

En este ejemplo:

El método busca en la lista el usuario cuyo ID coincida con el valor de `id`. Si se encuentra, devuelve el usuario; si no, devuelve un estado HTTP 404 (Not Found).

**@GetMapping(“/{id}”)**: Mapea la solicitud GET a la ruta `/api/usuarios/{id}`, donde `{id}` es un parámetro dinámico.

**@PathVariable Long id**: Captura el valor del parámetro `{id}` en la URL y lo pasa al método `obtenerUsuarioPorId`.