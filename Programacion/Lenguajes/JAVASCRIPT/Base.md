-Para crear dinamismo a los sitios web
-Orientado a objetos

video: 51:00

-----------------------------------------------------------------------------
Usos:
- IA
- Tecnologias frontend como angular, react o vue.js
- Mobiles apps
- Descktop apps
- Mas...

------------------------------------------------

Como enlazar a html javascript:
- Linea (no recomendable por la popularización)
```
<h1 onclick="alert('Hola')">Hola</h1>
```

- Etiquetas
```
<script>
        alert('Hola');
</script>
```

- Enlace o archivo .js
```
<script src="codigo.js"></script>
```

-------------------------------

Variables:
- var  --> global 
- let  --> mas loca
- const --> no pueden cambiar su valor despues(constante), de inicializa cuando se declara

```
const nombre = "Andrik";
alert(nombre);

let nombre = "Andrik";
alert(nombre);
```

Tipos de datos:
- Undeffined --> existe pero no esta definida o con un valor
- null --> se declara vacia la variable
- Nan --> cuando se quiere hacer una operacion sin que sean numeros

Uso de prompt:
- Promot es para pedir datos por una ventanita sencilla y la forma de guardar
```
let nombre = prompt("Ingresa tu nombre");
alert("Hola " + nombre);
```
![[Pasted image 20250106172224.png]]

