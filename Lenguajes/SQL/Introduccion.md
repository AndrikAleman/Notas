Entity -> El objeto
Attributes -> Las propiedades o caracteristicas

Tipos de relaciones:
- 1 to 1
- many to many
- 1 to many
- many to 1

Las restricciones semánticas también se llaman _reglas basadas en aplicaciones_ o _reglas de negocio_.

----------------------------------------------

DDL (Data Definition Language)
- Define, change, or drop data
- create, alter, truncate, drop



DML(Data Manipulation Langauges)
- read and modify data
- CRUD(Creare, Read, Update and Delete ROWS)
- Insert, select, update, delete

---------------------------

LIKE
Para saber algo que empieza o tiene una letra entre o al final es con LIKE

```
select firstname from author where firstname like 'R%'
```


RANGE
se usa between para un rango entre y entre
```
select title, pages from book where pages between 290 and 300
```

SE puede usar AND y OR
```
select firstname, lastname, country from author where country='AU' OR country='BR'
```

-------------------------------------------

ORDER BY
para ordenar por, DESC o ASC o tambien por la columna que queremos por ejemplo

```
selecr title, pages from book order by 2
```

Eliminar duplicados es con DISTINCT
```
select country from author order by 1

select distinct(country) from author
```


Para saber cuanto hay de algo es con Count y group by
```
select country, count(country) from author group by country
```

Renombrar algo es con AS
```
select country, count(country) as count from author group by country
```

Tambien se puede ocupar Having para saber cuanto tiene de tanto

----------------------------------------------

Usar múltiples tablas

JOIN
- Combinar dos o mas tablas
- basado en relaciones


## 1. **INNER JOIN**

Devuelve **solo las filas que tienen coincidencias** en ambas tablas.
### 🧩 Ejemplo:
```
SELECT empleados.nombre, departamentos.nombre FROM empleados INNER JOIN departamentos ON empleados.id_depto = departamentos.id;
```
✅ Devuelve solo los empleados que **sí tienen un departamento asignado**.

## 2. **LEFT JOIN** (o LEFT OUTER JOIN)
Devuelve **todas las filas de la tabla izquierda** y las que coinciden en la derecha. Si no hay coincidencia, los valores de la derecha serán **NULL**.
### 🧩 Ejemplo:
```
SELECT empleados.nombre, departamentos.nombre FROM empleados LEFT JOIN departamentos ON empleados.id_depto = departamentos.id;
```
✅ Devuelve **todos los empleados**, incluso si **no tienen departamento** (columna departamento aparecerá como NULL).

## 3. **RIGHT JOIN** (o RIGHT OUTER JOIN)
Devuelve **todas las filas de la tabla derecha** y las que coinciden en la izquierda. Si no hay coincidencia, los valores de la izquierda serán **NULL**.
### 🧩 Ejemplo:
```
SELECT empleados.nombre, departamentos.nombre FROM empleados RIGHT JOIN departamentos ON empleados.id_depto = departamentos.id;
```
✅ Devuelve todos los **departamentos**, aunque no tengan empleados.

## 4. **FULL JOIN** (o FULL OUTER JOIN)
Devuelve **todas las filas** cuando hay coincidencias **en una u otra tabla**. Si no hay coincidencia, se rellenan con NULL.
### 🧩 Ejemplo:
```
SELECT empleados.nombre, departamentos.nombre FROM empleados FULL JOIN departamentos ON empleados.id_depto = departamentos.id;
```
✅ Devuelve todos los empleados y todos los departamentos, incluso si **no están relacionados**.
> 🔔 _Nota:_ MySQL no soporta directamente `FULL JOIN`, pero puedes simularlo con `UNION` de `LEFT JOIN` y `RIGHT JOIN`.

