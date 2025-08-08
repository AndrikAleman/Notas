SQL -> Lenguaje de consultas estructurado (**Structured Query Language**)
-------------------------------------------------------------------------

**Descargar SQLite3**
1- Cuando se descarga lo pones en el disco donde esta windows o C:\
2- Crea una variable para entrar a sql

---------------------
Tipos de datos en SQLite3 (Es dinamico)

1- INTEGER (Números enteros INT)
2- TEXT (TEXTO O String)
3- BLOB (Datos bianrios, fotos, videos y mas)
4- Real (Double)
5- NUMERIC (números con mucha precisión y enormes, FLOAT)

Se creo la tabla de users, con nombre,  apellido y edad

--------------------------------

1- Ver todos los usuarios

```
SELECT * FROM usuarios;
```

```
SELECT nombre,edad FROM usuarios;
```


2- Insertar usuarios

```
INSERT INTO usuarios (nombre, apellido, edad) VALUES ("Andrik", "Aleman", 22), ("Jorge", "Sanchez", 30), ("Alan", "Perez", 34);
```

3- Eliminar todos los usuarios

```
DELETE FROM usuarios;
```

