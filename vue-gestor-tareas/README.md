# Vue-3---Semana-9---Gestor-de-tareas

Este proyecto es una aplicación de gestión de tareas construida con Vue.js. Permite a los usuarios agregar, mover y eliminar tareas en diferentes secciones: To do, Doing y Done.

## Estructura del Proyecto

- **src/assets**: Almacena recursos estáticos como imágenes y fuentes.
- **src/components/TaskInput.vue**: Componente para ingresar el nombre de una nueva tarea. Utiliza `v-model` para enlazar el valor del input y maneja eventos de botón y enter para agregar tareas.
- **src/components/TaskList.vue**: Muestra la lista de tareas dividida en tres secciones. Utiliza `v-for` para iterar sobre las tareas y `v-if` para mostrar un mensaje si no hay tareas registradas.
- **src/components/TaskColumn.vue**: Representa cada columna (To do, Doing, Done) y permite mover tareas entre secciones, eliminando tareas de la sección anterior al moverlas hacia adelante.
- **src/App.vue**: Componente raíz que importa y utiliza `TaskInput` y `TaskList`, gestionando el estado global de las tareas.
- **src/main.js**: Punto de entrada de la aplicación, configura Vue y monta la aplicación en el DOM.
- **src/styles/custom.css**: Contiene estilos personalizados para la aplicación, incluyendo colores y estilos para las diferentes secciones y tareas.
- **package.json**: Configuración de npm que lista las dependencias del proyecto y los scripts necesarios para ejecutar la aplicación.
- **vite.config.js**: Configuración para Vite, el bundler utilizado en el proyecto, definiendo opciones como el puerto de desarrollo y la configuración de plugins.

## Instrucciones de Instalación

1. Clona el repositorio en tu máquina local.
2. Navega al directorio del proyecto.
3. Ejecuta `npm install` para instalar las dependencias.
4. Ejecuta `npm run dev` para iniciar el servidor de desarrollo.
5. Abre tu navegador y visita `http://localhost:3000` para ver la aplicación en acción.

## Uso

- Agrega tareas utilizando el campo de entrada y presionando Enter o haciendo clic en el botón de agregar.
- Mueve las tareas entre las secciones arrastrándolas o utilizando los botones correspondientes.
- Elimina tareas de la sección anterior al moverlas hacia adelante.
- Si no hay tareas registradas, se mostrará un mensaje indicándolo.

## Contribuciones

Las contribuciones son bienvenidas. Si deseas mejorar este proyecto, por favor abre un issue o envía un pull request.