## Spring Boot**

**8.1** ¿Qué es Spring Boot?  
➡ Framework para crear apps Spring con configuración automática.

**8.2** Inyección de dependencias  
➡ Objeto entregado por el contenedor de Spring a otro objeto que lo necesita.

**8.3** Estereotipos  
➡ `@Component`: clase genérica.  
➡ `@Service`: lógica de negocio.  
➡ `@Repository`: acceso a datos.

**8.4** `@Autowired`  
➡ Inyecta automáticamente dependencias.

**8.5** Archivos de configuración  
➡ `application.properties` o `application.yml`.

**8.6** Bean  
➡ Objeto gestionado por Spring.

**8.7** `@RestController` vs `@Controller`  
➡ RestController: datos JSON/XML.  
➡ Controller: vistas HTML.

**8.8** Parámetros  
➡ `@PathVariable`: extrae de la URL.  
➡ `@RequestParam`: extrae de query.  
➡ `@RequestBody`: mapea JSON a objeto.

**8.9** Entidades JPA  
➡ `@Entity`: clase mapeada a tabla.  
➡ Relaciones: `@OneToMany`, `@ManyToOne`, `@ManyToMany`.

**8.10** JpaRepository  
➡ Métodos CRUD y consultas personalizadas.

**8.11** Paginación  
➡ `Pageable` y `Page<T>`.