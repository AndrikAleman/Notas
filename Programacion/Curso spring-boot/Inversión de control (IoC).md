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

