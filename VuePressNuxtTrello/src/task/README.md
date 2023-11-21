---
sidebar: auto
---


# Componente tarea

## TrelloBoardTask.vue

- En **components** crea el nuevo archivo **TrelloBoardTask.vue**

```vue
<script setup lang="ts">
import type { Task } from "@/types"
defineProps<{
    task: Task;
}>();   
</script>

<template>
  <div :title="task.createdAt.toLocaleDateString()"
    class="task bg-white p-2 mb-2 rounded shadow-sm max-w-[250px]"
  >
    <span>
      {{ task.title }}
    </span>
  </div>
</template>
```
## TrelloBoard.vue

Incluimos el **componente** tarea con su **Props** task

- En el archivo **TrelloBoard.vue**
- Modificamos:

```vue
<template>
  <div class="flex gap-4 overflow-x-auto items-start">
    <div v-for="column in columns" :key="column.id" 
    class="column bg-gray-200 p-5 rounded min-w-[250px]">
      <header class="font-bold mb-4">
       {{ column.title}} 
      </header>
      <TrelloBoardTask v-for="task in column.tasks" 
      :key="task.id" 
      :task="task" />
      <footer>
        <button class="text-gray-500">+ Add a Card</button>
      </footer>
    </div>
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
