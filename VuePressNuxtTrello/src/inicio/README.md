---
sidebar: auto
---

# Nuxt Trello Clon

## Introdución

Trello es una herramienta para el trabajo en equipo. 
Una lista de tareas. 
Igual ya te es  familiar.
Usa el método Kaban.
Método visual del flujo de trabajo.
Permite ver el progreso de diferentes tareas.
Puedes añadir nuevas columnas.
Reordenarlas, renombrarlas y añadir nuevas tareas.
En este curso vamos a construir una version mas simple
Vamos ha crear algo como esto.
Puedes añadir nuevas columnas.
Renombrar las que tienes.
Eliminar, recolocarlas y añadir nuevas tareas.
Arrastrar tareas entre diferentes columnas
O simplemente reordenarlas en la columna.
Al final tendremos un bonito panel de tareas Kaban o Trello

Vamos a utilizar la biblioteca Vue Draggable
Nos dota de  una fácil funcionalidad de arrastrar y soltar
Tu puedes hacer cosas como reordenar una lista
O arrastrar de una lista a otra una lista
Clonar o hacer una bonita transición.
En este caso trabajaremos con la biblioteca Sortable.JS
Usaremos vue Use.
Usaremos Tailwind CSS.

## Iniciando el proyecto

### Instalando Nuxt

Nuxt 3 [install](https://nuxt.com/docs/getting-started/installation)

Creo el proyecto con:
```
npx nuxi@latest init trello-tablero
```
![Instalar](../.vuepress/public/instalar.jpg)

- Contesto que si:
``` 
y
```

![Instalar](../.vuepress/public/npm.jpg)

- Elijo la opción:

```
npm
```
![Instalar](../.vuepress/public/participar.jpg)

- Contesto que no.

```
N
```
![Instalar](../.vuepress/public/carpeta.jpg)

- Selecciono la carpeta del proyecto.

- Ya lo puedo lanzar.

```
npm run dev
```

### Añadiendo módulos I

- Vamos al archivo **nuxt.config.ts**.
Aquí podemos definir los módulos que vamos a utilizar.
No necesitamos el server side rendering **ssr: false**.

```ts
// https://nuxt.com/docs/api/configuration/nuxt-config
export default defineNuxtConfig({
  modules:[],
  ssr: false,
  
  devtools: { enabled: true }
})
```
### Añadir dependencias

- Vamos a instalar algunas dependencias para nuestro proyecto.
    - Usaremos Tailwind CSS
    - Usaremos VueDraggable
    - Usaremos nanoID
    - Usaremos Vue-Use
    
```
npm i -D @nuxtjs/tailwindcss
```
```
npm i -S vuedraggable
```
```
npm i nanoid 
```
```
npm i @vueuse/nuxt
```
### Añadiendo módulos II

- Vamos a registrar los modulos:

```
modules:["@nuxtjs/tailwindcss", "@vueuse/nuxt"],
```

- Los otros son dependencias que importaremos directamente cuando las necesitemos.

- Finalmente ejecutaremos la aplicación

```
npm run dev
```