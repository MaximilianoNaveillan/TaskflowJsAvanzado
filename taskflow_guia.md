# 📘 Guía de Desarrollo

## Proyecto: TaskFlow --- Gestor de Tareas con JavaScript

Esta guía te ayudará a construir una aplicación paso a paso utilizando
**JavaScript moderno**.

La aplicación permitirá:

- crear tareas
- cambiar estado
- eliminar tareas
- almacenar información
- consumir datos desde una API

Durante el desarrollo aplicarás conceptos clave de:

- Programación orientada a objetos
- ES6+
- Manipulación del DOM
- Eventos
- Programación asíncrona
- Consumo de APIs

---

# 1️⃣ AE1 --- Orientación a Objetos en JavaScript

## 📚 Mini Lección

La **Programación Orientada a Objetos (POO)** es un paradigma que
permite organizar el código utilizando **objetos que representan
entidades del mundo real**.

En JavaScript, la POO se implementa principalmente mediante **clases**.

Una clase define:

- propiedades (datos)
- métodos (funciones)

### Ejemplo

```javascript
class Persona {
  constructor(nombre) {
    this.nombre = nombre;
  }

  saludar() {
    console.log('Hola soy ' + this.nombre);
  }
}

const p = new Persona('Ana');

p.saludar();
```

### Conceptos importantes

Concepto Descripción

---

class plantilla para crear objetos
constructor método que se ejecuta al crear una instancia
this referencia al objeto actual
método función dentro de una clase

📚
https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Classes

---

## 🧩 Ejercicio 1 --- Crear la clase Tarea

Debes crear una clase que represente una tarea.

Propiedades sugeridas:

- id
- descripcion
- estado
- fechaCreacion

💡 Pista

```javascript
class Tarea {
  constructor(id, descripcion) {
    this.id = id;
    this.descripcion = descripcion;

    // estado inicial de la tarea

    // fecha de creación
  }
}
```

---

## 🧩 Ejercicio 2 --- Método cambiarEstado()

Cada tarea debe poder alternar entre:

- pendiente
- completada

```javascript
cambiarEstado(){

  this.estado = this.estado === "pendiente"
    ? "completada"
    : "pendiente"

}
```

---

## 🧩 Ejercicio 3 --- Clase GestorTareas

```javascript
class GestorTareas {
  constructor() {
    this.tareas = [];
  }
}
```

---

# 2️⃣ AE2 --- Características JavaScript ES6+

## 📚 Mini Lección

**ES6 (ECMAScript 2015)** introdujo muchas mejoras que hacen el código
más limpio y moderno.

### Características principales

Característica Uso

---

let variables reasignables
const constantes
arrow functions funciones más cortas
template literals strings dinámicos
destructuring extraer propiedades
spread operator copiar o combinar objetos

### Ejemplo

```javascript
const nombre = 'Juan';

const mensaje = `Hola ${nombre}`;

console.log(mensaje);
```

📚 https://developer.mozilla.org/es/docs/Web/JavaScript/Guide

---

## 🧩 Ejercicio 1 --- Reemplazar var

```javascript
const gestor = new GestorTareas();
```

---

## 🧩 Ejercicio 2 --- Template literals

```javascript
const texto = `${tarea.descripcion} - ${tarea.estado}`;
```

---

## 🧩 Ejercicio 3 --- Arrow functions

Antes

```javascript
function eliminarTarea(id) {}
```

Después

```javascript
const eliminarTarea = (id) => {};
```

---

## 🧩 Ejercicio 4 --- Destructuring

```javascript
const { id, descripcion, estado } = tarea;
```

---

# 3️⃣ AE3 --- Eventos y Manipulación del DOM

## 📚 Mini Lección

El **DOM (Document Object Model)** es una representación estructurada
del documento HTML.

Permite a JavaScript:

- modificar contenido
- agregar elementos
- eliminar elementos
- reaccionar a eventos

### Ejemplo

```javascript
const boton = document.querySelector('button');

boton.addEventListener('click', () => {
  console.log('Botón presionado');
});
```

📚 https://developer.mozilla.org/es/docs/Web/API/Document_Object_Model

---

## 🧩 Ejercicio 1 --- Crear la estructura HTML

```html
<h1>TaskFlow</h1>

<form id="formulario">
  <input type="text" id="tarea" />

  <button>Agregar</button>
</form>

<ul id="lista"></ul>
```

---

## 🧩 Ejercicio 2 --- Capturar submit

```javascript
formulario.addEventListener('submit', (e) => {
  e.preventDefault();
});
```

---

## 🧩 Ejercicio 3 --- Crear elementos dinámicamente

```javascript
const li = document.createElement('li');

const span = document.createElement('span');

span.textContent = tarea.descripcion;

li.appendChild(span);
```

---

## 🧩 Ejercicio 4 --- Eventos adicionales

### mouseover

```javascript
li.addEventListener('mouseover', () => {
  li.style.background = '#eee';
});
```

### keyup

```javascript
input.addEventListener('keyup', (e) => {
  console.log(e.target.value);
});
```

---

# 4️⃣ AE4 --- JavaScript Asíncrono

## 📚 Mini Lección

JavaScript utiliza un **modelo asincrónico basado en eventos**.

Esto significa que ciertas operaciones pueden ejecutarse **sin bloquear
el programa**.

Función Uso

---

setTimeout ejecutar después de un tiempo
setInterval ejecutar repetidamente
Promise representar operaciones futuras
async/await simplificar promesas

### Ejemplo

```javascript
setTimeout(() => {
  console.log('mensaje después de 2 segundos');
}, 2000);
```

📚 https://developer.mozilla.org/es/docs/Learn/JavaScript/Asynchronous

---

## 🧩 Ejercicio 1 --- Simular retardo

```javascript
setTimeout(() => {
  console.log('tarea agregada');
}, 2000);
```

---

## 🧩 Ejercicio 2 --- Notificación

```javascript
setTimeout(() => {
  alert('Tarea guardada');
}, 2000);
```

---

## 🧩 Ejercicio 3 --- Intervalo

```javascript
setInterval(() => {
  console.log('verificando tareas');
}, 5000);
```

---

# 5️⃣ AE5 --- Consumo de APIs

## 📚 Mini Lección

Una **API (Application Programming Interface)** permite que aplicaciones
se comuniquen entre sí.

En el navegador se usa principalmente **fetch()** para hacer solicitudes
HTTP.

### Ejemplo

```javascript
fetch('https://api.com/datos')
  .then((response) => response.json())
  .then((data) => console.log(data));
```

También existe la sintaxis moderna:

```javascript
async function obtenerDatos() {
  const response = await fetch('url');

  const data = await response.json();
}
```

Usaremos la API pública **JSONPlaceholder**.

📚 https://developer.mozilla.org/es/docs/Web/API/Fetch_API

---

## 🧩 Ejercicio 1 --- Obtener datos desde API

```javascript
async function obtenerTareas() {
  const response = await fetch('https://jsonplaceholder.typicode.com/todos?_limit=5');

  const data = await response.json();

  console.log(data);
}
```

---

## 🧩 Ejercicio 2 --- Manejo de errores

```javascript
try {
  // fetch
} catch (error) {
  console.error(error);
}
```

---

## 🧩 Ejercicio 3 --- Guardar en localStorage

```javascript
localStorage.setItem('tareas', JSON.stringify(tareas));
```

📚 https://developer.mozilla.org/es/docs/Web/API/Window/localStorage

---

# 📦 Entregable Final

La aplicación debe permitir:

- Crear tareas
- Cambiar estado
- Eliminar tareas
- Guardar tareas en almacenamiento local
- Consumir datos desde una API
- Interactuar con el usuario mediante eventos

---

# 💼 Portafolio

Sube el proyecto a **GitHub** destacando habilidades en:

- JavaScript
- manipulación del DOM
- asincronía
- consumo de APIs
