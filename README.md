# 🚀 Proyecto Integrador ABP Módulo 5

# TaskFlow - Aplicación de Gestión de Tareas en JavaScript

## 📌 Contexto

El Departamento de Desarrollo Web necesita desarrollar una aplicación
interactiva para gestionar tareas utilizando JavaScript moderno (ES6+),
aplicando:

- Programación Orientada a Objetos (POO)
- Manipulación del DOM
- Manejo de eventos
- Buenas prácticas de estructura y organización

⚠️ En esta etapa NO se considerará: - Programación asíncrona - Consumo
de APIs

---

# 🎯 Objetivo

Desarrollar una aplicación web que permita:

✔ Crear tareas\
✔ Editar tareas\
✔ Eliminar tareas\
✔ Cambiar estado de tareas (pendiente / completada)\
✔ Manipular dinámicamente el DOM\
✔ Aplicar principios de POO

---

# 🏗️ Estructura del Proyecto

Se recomienda la siguiente estructura:

taskflow/ │ ├── index.html ├── css/ │ └── styles.css └── js/ └── app.js

---

# 🧠 Paso 1: Orientación a Objetos en JavaScript

## 1️⃣ Crear la clase `Tarea`

Propiedades sugeridas: - id - descripcion - estado - fechaCreacion

Pistas: - Usa constructor() - Usa this para asignar propiedades - Genera
el id con Date.now()

Métodos sugeridos: - cambiarEstado() -
editarDescripcion(nuevaDescripcion)

---

## 2️⃣ Crear la clase `GestorTareas`

Responsabilidad: Administrar un arreglo de tareas.

Propiedad: - this.tareas = \[\]

Métodos sugeridos: - agregarTarea(descripcion) - eliminarTarea(id) -
obtenerTareas() - cambiarEstado(id)

Pistas: - Usa push() para agregar - Usa filter() para eliminar - Usa
find() para buscar por id - Usa map() si necesitas transformar datos

---

# ✨ Paso 2: Aplicar Características ES6+

Buenas prácticas obligatorias:

✔ Usar let y const\
✔ Template literals\
✔ Arrow functions\
✔ Destructuring\
✔ Spread operator

Ejemplo conceptual:

const { id, descripcion } = tarea; const nuevasTareas =
\[...this.tareas\];

---

# 🖥️ Paso 3: Manipulación del DOM

HTML base mínimo:

```{=html}
<form id="form-tarea">
```

`<input type="text" id="input-tarea" />`{=html}
`<button type="submit">`{=html}Agregar`</button>`{=html}

```{=html}
</form>
```

```{=html}
<ul id="lista-tareas">
```

```{=html}
</ul>
```

Métodos importantes: - document.getElementById() -
document.querySelector() - document.createElement() - appendChild() -
innerHTML - classList.add() - remove()

Crear función renderizarTareas():

- Limpiar contenedor
- Recorrer tareas con forEach()
- Crear elementos
  ```{=html}
  <li>
  ```
- Agregar botones dinámicamente

---

# 🖱️ Paso 4: Manejo de Eventos

Evento submit: - Usar e.preventDefault() - Obtener valor input - Validar
que no esté vacío - Agregar tarea - Renderizar - Limpiar input

Evento click: - Botón completar - Botón eliminar - Puede usarse
delegación de eventos

Evento mouseover: - Cambiar estilos dinámicamente

Evento keyup: - Detectar escritura en tiempo real

# ⚙️Paso 5: CONSUMO DE APIS CON JAVASCRIPT

Objetivo: Integrar una API externa para mejorar la aplicación.

● Usar `fetch()` para obtener datos de una API de tareas.  
● Implementar métodos asincrónicos en la clase `GestorTareas` para sincronizar datos.  
● Utilizar `async/await` para manejar las peticiones.  
● Manejar errores con `try/catch` y mostrar mensajes en la interfaz.  
● Guardar y recuperar tareas utilizando `localStorage`.  
● Sincronizar tareas entre la API y el estado interno de la aplicación.

## **Entrega:** Aplicación funcional con consumo de API implementado, manejo de errores y persistencia de datos en `localStorage`.

# 📌 Qué se Evaluará

✔ Correcta implementación de clases\
✔ Separación de responsabilidades\
✔ Uso de ES6+\
✔ Manipulación correcta del DOM\
✔ Manejo adecuado de eventos\
✔ Código limpio y organizado

---

# 💼 Recomendación Final

1.  Crear repositorio en GitHub\
2.  Subir código organizado\
3.  Agregar capturas en el README\
4.  Explicar:
    - Cómo funciona
    - Qué conceptos aplicaste
    - Qué fue lo más desafiante

**Entrega:** Aplicación funcional con consumo de API implementado, manejo de errores y persistencia de datos en `localStorage`.

## ¿Qué vamos a validar? 🔍

● Correcta aplicación de la orientación a objetos.  
● Uso de ES6+ en la implementación del código.  
● Interactividad lograda a través del manejo de eventos.  
● Correcto manejo de asincronía.  
● Implementación y validación del consumo de APIs.

---

## Referencias 🦺

● MDN JavaScript  
● Guía de ECMAScript 6  
● JSONPlaceholder API

---

## Recursos 🎁

● POO en JavaScript - Artículo  
● fetch() y manejo de promesas - Documentación  
● Ejemplo de aplicación en GitHub

---

Pág. 4

## Entregables ✅

● Código fuente documentado.  
● Demostración funcional.  
● Explicación del código en un informe breve.

---

🔥 Este proyecto será una pieza clave en tu portafolio como
desarrollador JavaScript.

🤔ayuda.
Puedes usar la API: [ ir a Jsonplaceholder ](https://jsonplaceholder.typicode.com/)

GET https://jsonplaceholder.typicode.com/todos

GET https://jsonplaceholder.typicode.com/todos/1

POST https://jsonplaceholder.typicode.com/todos

PUT https://jsonplaceholder.typicode.com/todos/1

DELETE https://jsonplaceholder.typicode.com/todos/1
