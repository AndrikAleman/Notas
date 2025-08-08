### @Autowired: La Anotación Clave para la Inyección de Dependencias

Es una anotacion que se utiliza para inyectar automáticamente dependencias en un bean gestionado por Spring 

**Uso de @Autowired:** Spring escanea los beans en tu aplicación y los inyecta en los puntos donde se ha especificado **@Autowired**.

Ejemplo:
```
@Service
public class SaludoService {
 
    @Autowired
    private SaludoRepository saludoRepository;
 
    public String obtenerSaludo() {
        return saludoRepository.findSaludo();
    }
}
```

En este ejemplo, **@Autowired** indica que `saludoRepository` debe ser inyectado por Spring. Spring buscará una instancia de `SaludoRepository` en su contenedor y la inyectará automáticamente.

