### @Service: Lógica de Negocio

**@Service**: Especialidad de @Component para indicar que una clase tiene logica de negocio. Buena practica para dejar claro el servicio en tu arquitectura y que realiza tu clase

**Uso común**: Encapsular la lógica de negocio y operaciones de procesamiento que no pertenecen a la capa de control ni a la capa de acceso a datos.

```
@Service
public class SaludoService {
    public String obtenerSaludo() {
        return "Hola desde el servicio!";
    }
}
```
