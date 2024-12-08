(Lenguaje de consulta estructurado)

==Table==
```
CREATE TABLE employees ( 
Id INT AUTO_INCREMENT PRIMARY KEY, 
first_name VARCHAR(50) NOT NULL, 
last_name VARCHAR(50) NOT NULL, 
email VARCHAR(100) UNIQUE NOT NULL, 
phone_number VARCHAR(15), 
hire_date DATE NOT NULL, 
job_title VARCHAR(50) NOT NULL, 
salary DECIMAL(10, 2) NOT NULL, 
department_id INT
);
```

![[Pasted image 20241207184221.png]]

Comandos mas utilizados de mysql.
- ![[Pasted image 20241202173050.png]]

Para ver todos los registros de una tabla
```
SELECT * FROM employees;
```

Para ver alguna columna de alguna tabla en concreto.
```
SELECT name FROM employees;
```

Ver registros distintos( sin cosas duplicadas ), ==SELECT DISTINCT==
```
SELECT DISTINCT name, lastname FROM employees;
```

Ver en números los distintos registros que existen sin duplicados, ==SELECT COUNT==
```
SELECT COUNT ( DISTINCT name) FROM  employees;
```


==WHERE==
Es para especificar que tipo de dato requiero
```
SELECT name FROM employees WHERE name = 'jose';
```
```
SELECT * FROM employees WHERE EmpleadosId = 10;
```


Operadores para ==WHERE==
![[Pasted image 20241202174758.png]]

**==Operadores ternarios==**

Los principales operadores ternarios son: AND, OR, NOT

AND Sintaxis.
```
SELECT name, lastName FROM employees WHERE name = 'jose' AND lastName = 'santiago';
```

OR Sintaxis.
```
SELECT name, lastName FROM employees WHERE name = 'jose' OR name = 'Andrik';
```

NOT Sintaxis.
```
SELECT name, lastName FROM employees WHERE NOT name = 'jose';
```

Examples.
```
SELECT * FROM Customers  
WHERE Country = 'Germany' AND (City = 'Berlin' OR City = 'Stuttgart');

SELECT * FROM Customers  
WHERE NOT Country = 'Germany' AND NOT Country = 'USA';
```


**==ORDER BY==**
- Esta keyword es usada para ordenar de forma ascendente y descendente.
	- DESC
	- ASC

```
SELECT Id, name FROM employees ORDER BY  Id DESC;

SELECT * FROM employees ORDER BY Country ASC, CustomerName DESC;
```

**==INSERT INTO==**
- Su principal función es insertar un nuevo elemento a una tabla
```
INSERT INTO employees (first_name, last_name, email, phone_number, hire_date, job_title, salary, department_id) VALUES
('John', 'Doe', 'john.doe@example.com', '123-456-7890', '2023-06-01', 'Software Engineer', 80000.00, 1);
```

**==NULL Values==**



Bibliografia.
[MySQL SELECT Statement](https://www.w3schools.com/mysql/mysql_null_values.asp)
