---
sidebar: auto
---


# Draggable Columnas

## Archivo TrelloBoard.vue

- Importamos la dependencia **draggable**

```ts
import draggable from "vuedraggable"
```
## TrelloBoard.vue

```vue
<template>
  <div>
     <draggable
      v-model="columns"
      group="columns"
      :animation="150"
      handle=".drag-handle"
      item-key="id"
      class="flex gap-4 items-start"
    >
      <template #item="{ element: column }:  { element: Column }">
        <div class="column bg-gray-200 p-5 rounded min-w-[250px]">
          <header class="font-bold mb-4">
            <drag-handle />
          {{ column.title}} 
          </header>
      <TrelloBoardTask v-for="task in column.tasks" 
      :key="task.id" 
      :task="task" />
      <footer>
        <button class="text-gray-500">+ Add a Card</button>
      </footer>
    </div>
    </template>
    </draggable>
  </div>  
</template>
```

## App.vue

Incluimos una imangen corporativa y un título de página.

- En el archivo **App.vue**
- Modificamos:

```vue
<template>
  <div class="p-5 h-[100vh] bg-teal-600 over-flow-auto">  
    <h1 class="text-2xl text-white flex items-center mb-10">
      <img width="200" class="mr-3" src="/vue.png" alt="Vue.js-ES">
      Trello-Tablero
    </h1>
    <trello-board />
  </div>
</template>
```
