### @Repository: Acceso a Datos

@Repository -> Se utiliza para la capa de acceso de datos. Permite  Spring tratar las excepciones de acceso de datos y proporcionar soporte para operaciones con bases de datos

**Uso común**: Gestionar la interacción con la base de datos, incluyendo consultas y operaciones CRUD (crear, leer, actualizar, eliminar).

```
@Repository
	public interface UsuarioRepository extends JpaRepository<Usuario, Long> {
    // Métodos personalizados de acceso a la base de datos
}
```
