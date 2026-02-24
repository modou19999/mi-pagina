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
