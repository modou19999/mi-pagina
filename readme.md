Aquí tienes un resumen sencillo y ordenado para estudiar Semana 1 y 2 – JS en la Web 👇

🌐 SEMANA 1 – JS EN LA WEB
1️⃣ ¿Cómo funciona la Web?
🏗 Arquitectura web (modelo básico)

Cliente → Navegador

Servidor → Envía HTML, CSS, JS

Comunicación por HTTP

🌍 Navegador web

Cuando llega el HTML, el navegador hace:

Parse → Convierte el HTML en un árbol llamado DOM

Render (Layout) → Calcula tamaños y posiciones

Paint → Dibuja todo en pantalla

2️⃣ Conceptos básicos de JavaScript
📦 Datos y variables

let → variable que cambia

const → variable que no cambia referencia

🔢 Tipos de datos

Primitivos: string, number, boolean, null, undefined

Objetos: arrays, funciones, objetos

⚖ Comparaciones

== → compara valor

=== → compara valor y tipo (mejor usar esta)

3️⃣ Modelo mental de JS
🧠 Variables guardan:

Valores primitivos → copia independiente

Objetos → referencia (apuntan al mismo lugar)

🔄 Mutabilidad

Arrays y objetos → mutables (se pueden modificar)

Primitivos → inmutables

4️⃣ Funciones

Pueden recibir parámetros

Pueden devolver valores

Pueden recibir otras funciones → callbacks

Ejemplo mental:

Una función puede ejecutar otra función.

🌳 JS EN LA WEB – DOM
📌 ¿Qué es el DOM?

Es la representación del HTML como árbol de nodos.

🔎 Acceso a elementos
Métodos modernos (mejor opción)

querySelector()

querySelectorAll()

Métodos antiguos

getElementById()

getElementsByClassName()

Diferencia:

NodeList → resultado de querySelectorAll

HTMLCollection → resultado de getElementsBy...

🔁 Modificar elementos
Contenido

textContent → solo texto

innerHTML → cambia el contenido interno (interpreta HTML)

outerHTML → reemplaza el elemento completo

Atributos

element.setAttribute()

element.getAttribute()

Clases

classList.add()

classList.remove()

classList.toggle()

🖱 Eventos

Un evento ejecuta un callback.

Ejemplo:

click

submit

input

📚 Métodos de Array
🔴 Mutables (cambian el array)

push()

sort()

🟢 Inmutables (devuelven nuevo array)

map()

filter()

find()

forEach()

toSorted()

🎮 Proyecto: Tres en raya

Se aprendió:

Uso de arrays para comprobar ganador

Eventos click

Manipulación del DOM

Separar lógica y vista

📝 Formularios

<input>

Capturar valores

Evento submit

Validaciones

🌐 SEMANA 2 – COMPONENTES Y DATOS
📦 JSON

Formato de texto para datos.

JSON.stringify() → objeto a texto

JSON.parse() → texto a objeto

🧭 Routing (Enrutamiento)

Permite mostrar diferentes páginas según la URL.

Basado en location.pathname

Rutas relativas al servidor

Carga dinámica de JS

🧩 Componentes

Un componente:

Es una función

Devuelve HTML (template string)

Puede recibir parámetros

Ejemplo mental:

Una función que devuelve una tarjeta HTML.

Insertar HTML dinámicamente

insertAdjacentHTML()

🗂 CRUD – ToDo List

CRUD significa:

Create → crear

Read → leer

Update → actualizar

Delete → eliminar

Conceptos importantes:

Modelo (Entidad)

Mock de datos (JSON)

Componentes reutilizables

Funciones como parámetros

⏳ Asincronía en JS

JS puede hacer cosas que tardan tiempo.

1️⃣ Callbacks

Funciones que se ejecutan después.

2️⃣ setTimeout

Ejecuta algo después de un tiempo.

3️⃣ Promesas

Representan un valor futuro:

pending

resolved

rejected

4️⃣ async / await

Forma más clara de trabajar con promesas.

5️⃣ Manejo de errores

try / catch

🌍 APIs REST

Una API devuelve datos normalmente en JSON.

Ejemplo usado:

https://pokeapi.co/api/v2/pokemon/ditto

📡 AJAX

Forma antigua:

XMLHttpRequest

Forma moderna:

fetch()

🖥 Modelos de Renderizado
🏗 SSR (Server Side Rendering)

El servidor genera el HTML cuando se pide.

⚡ CSR (Client Side Rendering)

El navegador genera el HTML con JS.

🧊 SSG (Static Site Generation)

El HTML se genera antes (en build).

🧠 Ideas clave para examen

Entender cómo funciona el DOM

Diferencia entre mutable e inmutable

Saber usar arrays

Entender callbacks y async/await

Saber manipular HTML con JS

Entender qué es un componente

Comprender CRUD

Diferencia entre SSR, CSR y SSG

Si quieres, puedo hacerte:

📝 Un resumen todavía más corto tipo “chuleta”

🧪 Preguntas tipo examen

🧠 Esquema visual

💻 Mini ejercicios prácticos para repasar

___________________________________
🏗 Proyecto: Mini ToDo List con DOM y JS

Objetivo: Crear una lista de tareas donde puedas agregar, eliminar, y marcar completadas tareas usando JS puro.

1️⃣ HTML básico
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Mini ToDo List</title>
  <style>
    .done { text-decoration: line-through; }
  </style>
</head>
<body>
  <h1>Mi Lista de Tareas</h1>

  <!-- Formulario para agregar tareas -->
  <form id="todo-form">
    <input type="text" id="todo-input" placeholder="Nueva tarea" required>
    <button type="submit">Agregar</button>
  </form>

  <!-- Lista de tareas -->
  <ul id="todo-list"></ul>

  <script src="app.js"></script>
</body>
</html>

Explicaciones:

<form> → Captura la entrada del usuario.

input → Aquí escribes la tarea.

button type="submit" → Envía el formulario.

<ul> → Lista donde pondremos las tareas.

.done → Clase CSS para marcar tareas completadas.

2️⃣ JS – Variables y acceso al DOM
// Referencias al DOM
const form = document.querySelector('#todo-form') // selecciona el formulario
const input = document.querySelector('#todo-input') // selecciona el input
const list = document.querySelector('#todo-list')   // selecciona la lista de tareas

// Array que guarda todas las tareas
let todos = []  // mutable, podemos agregar o eliminar

Explicaciones:

querySelector → selecciona elementos por id.

todos → Array donde guardaremos las tareas (mutable).

3️⃣ JS – Función para renderizar tareas
function renderTodos() {
  list.innerHTML = '' // limpia la lista antes de dibujar
  todos.forEach((todo, index) => {
    // Crea un <li> para cada tarea
    const li = document.createElement('li')
    li.textContent = todo.text

    // Marca la tarea completada si corresponde
    if (todo.done) {
      li.classList.add('done')
    }

    // Botón para eliminar tarea
    const deleteBtn = document.createElement('button')
    deleteBtn.textContent = 'Eliminar'
    deleteBtn.addEventListener('click', () => deleteTodo(index))

    // Evento para marcar como completada
    li.addEventListener('click', () => toggleDone(index))

    li.appendChild(deleteBtn)
    list.appendChild(li)
  })
}

Explicaciones línea por línea:

list.innerHTML = '' → Limpia todo para evitar duplicados.

forEach → Recorre cada tarea en el array.

document.createElement('li') → Crea un nuevo nodo HTML.

li.textContent = todo.text → Pone el texto de la tarea.

if (todo.done) → Aplica clase .done si la tarea está hecha.

deleteBtn.addEventListener('click', ...) → Callback para eliminar la tarea.

li.addEventListener('click', ...) → Callback para marcar como completada.

li.appendChild(deleteBtn) → Añade el botón al <li>.

list.appendChild(li) → Añade el <li> a la lista visible.

4️⃣ JS – Funciones CRUD
✅ Agregar tarea
form.addEventListener('submit', (e) => {
  e.preventDefault() // evita recargar la página
  const text = input.value.trim() // elimina espacios extra
  if (text) {
    todos.push({ text, done: false }) // agregamos tarea al array
    input.value = '' // limpia el input
    renderTodos() // actualiza la lista
  }
})

Explicaciones:

e.preventDefault() → Evita que el formulario recargue la página.

trim() → Quita espacios al inicio y fin.

todos.push(...) → Agrega la tarea al array (mutable).

renderTodos() → Redibuja la lista completa.

✅ Eliminar tarea
function deleteTodo(index) {
  todos.splice(index, 1) // elimina un elemento del array
  renderTodos()           // actualiza la lista
}

Explicaciones:

splice(index, 1) → elimina 1 elemento en la posición index.

renderTodos() → se vuelve a dibujar la lista actualizada.

✅ Marcar como completada
function toggleDone(index) {
  todos[index].done = !todos[index].done // cambia true/false
  renderTodos()
}

Explicaciones:

!todos[index].done → alterna entre true y false.

Se vuelve a dibujar la lista para reflejar cambios.

5️⃣ JS – Simulación de async/fetch (opcional)

Si quieres practicar fetch y promesas, podemos simular carga de tareas desde un API:

async function loadTodos() {
  try {
    const res = await fetch('https://jsonplaceholder.typicode.com/todos?_limit=5')
    const data = await res.json()
    todos = data.map(todo => ({ text: todo.title, done: todo.completed }))
    renderTodos()
  } catch (err) {
    console.error('Error cargando tareas', err)
  }
}

loadTodos()

Explicaciones:

async/await → manejar promesas de forma clara.

fetch() → obtiene datos de la web.

try/catch → manejo de errores.

data.map(...) → transforma los datos para que tengan la misma estructura que nuestro array.

✅ Qué practicas con este proyecto

Variables, arrays, objetos

Mutabilidad e inmutabilidad

DOM: createElement, textContent, appendChild, innerHTML

Eventos: click, submit, callbacks

Funciones CRUD: agregar, eliminar, actualizar

Condicionales y clases CSS (done)

Async/await y fetch

Iteración con forEach, map

Limpieza de inputs y renderizado dinámico

Si quieres, puedo hacer una versión “ultra comentada línea por línea” lista para copiar y practicar, con tips de examen y mini retos en cada línea, para que practiques todo en un solo archivo.

¿Quieres que haga esa versión completa?
