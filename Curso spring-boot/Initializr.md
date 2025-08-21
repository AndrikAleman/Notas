Es una herramienta para generar un proyecto de spring, donde puede generar la version de spring y dependencias que tiene

![[Pasted image 20250504175209.png]][https://start.spring.io/](https://start.spring.io/)

**Detalles del proyecto**
---------------------------------------------------------------------------------------

**Group**: Especifica el nombre del grupo o paquete base
**Artifact**: define el nombre de la aplicacion o proyecto
**Name**: Este campo suele coincidir con el Artifact, peropeudes cambiarlo.
**Description**: Escribe una breve descripcion del proyecto.
**Package Name**: Generalmente, este genera automaticamente basado en el Group y Artifact
**Packaging**: Elige entre Jar(Recomendado para la mayoria de aplicaciones) o War(Para desplegar un servidor de Java)
**Java version**: Selecciona la versión Java

-----------------------------


Dependencias
--------------------------------
**Spring web**: Para crear aplicaciones web y REST APIs
**Spring Data JPA**: Para integraciones con bases de datos utilizando JPA y Hibernate
**Spring Boot DevTools**: Herramientas para mejorar el desarrollo como recargar automaticamente
**Spring Security**: Para añadir seguidad a tus aplicaciones

Estructura del proyecto
---------------------------------------------
mi-proyecto-spring
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com.ejemplo
│   │   │       └── MiProyectoSpringApplication.java
│   │   └── resources
│   │       ├── application.properties
│   │       └── static/
│   │       └── templates/
│   └── test
│       └── java
│           └── com.ejemplo
│               └── MiProyectoSpringApplicationTests.java
└── pom.xml


Anotaciones
----------------------------------------------------
**@Component: La anotación genérica**
Las anotaciones permiten que Spring identifique, escanear y gestionar los objetos de manera automática.

**@Component** -> Es la anotación mas genérica  y sirve para declarar cualquier clase como un bean manejado por el contenedor de Spring

**@Controller**, **@Service** y **@Repository** son especializaciones de **@Component**

```
@Component
public class MiComponente {
    public void realizarTarea() {
        System.out.println("Ejecutando una tarea en MiComponente.");
    }
}
```

-----------------

## Interacción entre @Controller, @Service y @Repository

En una aplicación Spring Boot bien organizada, estas anotaciones representan las capas principales:

1. **@Controller** (Capa de Presentación): Gestiona las solicitudes HTTP y coordina la respuesta.
2. **@Service** (Capa de Negocio): Contiene la lógica de negocio.
3. **@Repository** (Capa de Acceso a Datos): Se encarga de la interacción con la base de datos.

```
// Capa de Acceso a Datos (Repository)
@Repository
public interface UsuarioRepository extends JpaRepository<Usuario, Long> {
    Optional<Usuario> findByNombre(String nombre);
}
 
// Capa de Negocio (Service)
@Service
public class UsuarioService {
   
    @Autowired
    private UsuarioRepository usuarioRepository;
   
    public Usuario obtenerUsuarioPorNombre(String nombre) {
        return usuarioRepository.findByNombre(nombre)
                                .orElseThrow(() -> new RuntimeException("Usuario no encontrado"));
    }
}
 
// Capa de Presentación (Controller)
@Controller
public class UsuarioController {
   
    @Autowired
    private UsuarioService usuarioService;
   
    @GetMapping("/usuario/{nombre}")
    public String obtenerUsuario(@PathVariable String nombre, Model model) {
        Usuario usuario = usuarioService.obtenerUsuarioPorNombre(nombre);
        model.addAttribute("usuario", usuario);
        return "detalleUsuario";
    }
}
```

- El **@Controller** maneja las solicitudes HTTP.
- El **@Service** contiene la lógica de negocio.
- El **@Repository** se encarga de las operaciones con la base de datos.


----------------------------
### Inversión de control (IoC)
Es un principio de diseño que transfiere la responsabilidad de gestionar los objetos y sus dependencias desde la aplicación al Framewok.

En lugar de que tu código cree e instancie objetos directamente, IoC permite que un contenedor (Como el de spring) gestione la creación, configuración y ciclo de vida de los objetos


En otras palabras, IoC cambia el flujo de control en una aplicación, permitiendo que Spring tome decisiones sobre la creación y gestión de los objetos, mientras que tú te concentras en escribir la lógica de negocio.


### Inyección de Dependencias (DI)

Tecnica mediante el cual se implementa IoC, consiste en proporcionar las dependencias de un objeto en lugar de que el objeto las cree por si mismo 

Formas de inyectar dependencias en Spring.

- 1. **Inyección por Constructor:** Las dependencias se pasan a través del constructor de la clase.
```
@Service
public class MiServicio {
    private final MiRepositorio miRepositorio;
 
    // Inyección de dependencias por constructor
    @Autowired
    public MiServicio(MiRepositorio miRepositorio) {
        this.miRepositorio = miRepositorio;
    }
}
```

- 1. **Inyección por Setter:** Las dependencias se inyectan a través de métodos setter.
```
@Service
public class MiServicio {
 
    private MiRepositorio miRepositorio;
 
    // Inyección de dependencias por setter
    @Autowired
    public void setMiRepositorio(MiRepositorio miRepositorio) {
        this.miRepositorio = miRepositorio;
    }
}
```

- 1. **Inyección por Campo (Field Injection):** Las dependencias se inyectan directamente en los campos de la clase.
```
@Service
public class MiServicio {
 
    @Autowired
    private MiRepositorio miRepositorio;
}
```


---
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


---
### Tipos de Inyección de Dependencias

Spring proporciona varias maneras de resolver la inyección de dependencias:

- **Inyección por Tipo:** Spring intenta inyectar un bean que coincida con el tipo del campo o parámetro.
- **Inyección por Nombre:** Cuando hay varios beans del mismo tipo, Spring puede usar el nombre del bean para resolver la inyección.


Si existen múltiples beans del mismo tipo, puedes usar **@Qualifier** para especificar cuál bean deseas inyectar:

```
@Autowired
@Qualifier("miBeanEspecifico")
private MiRepositorio miRepositorio;
```

