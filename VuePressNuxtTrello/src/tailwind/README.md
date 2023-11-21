---
sidebar: auto
---


# TailWind CSS 

## Clases

### TrelloBoard.vue

- En **components** archivo **TrelloBoard.vue**

```vue
<template>
  <div class="flex gap-4 overflow-x-auto items-start">
    <div v-for="column in columns" :key="column.id" 
    class="column bg-gray-200 p-5 rounded min-w-[250px]">
      <header>
       {{ column.title}} 
      </header>
      <p v-for="task in column.tasks" :key="task.id">
        {{ task.title }}
      </p>
    </div>
  </div>  
</template>
```

### App.vue

- En el archivo **App.vue**
- Modificamos:

```vue
<template>
  <div class="p-5 h-[100vh] bg-teal-600 over-flow-auto">
    <trello-board />
  </div>
</template>
```