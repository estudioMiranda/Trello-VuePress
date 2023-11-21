---
sidebar: auto
---

## Datos TypeScript

### Carpeta Types y archivo index.ts

- Creemos una carpeta llamada **types**
- Creemos un archivo llamado **index.ts**

```ts
export type ID = string;

export interface Column {
    title: string;
    id: ID;
    task: Task[];
}

export interface Task {
    id: ID;
    title: string;
    createdAt: Date;
}
```

### Carpeta Componentes y archivo TrelloBoard.vue

- Creemos una carpeta **components**
- Creemos un archivo llamado **TrelloBoard.vue**

```vue
<script setup lang="ts">
import { ref } from "vue";
import type { Column } from "../types/index";

import { nanoid } from "nanoid";

const columns = ref<Column[]>([
    {
    id: nanoid(),
    title: "Columna 1",
    tasks: [
        {
        id: nanoid(),
        title: "Tarea 1",
        createdAt: new Date()
        },
         {
        id: nanoid(),
        title: "Tarea 2",
        createdAt: new Date()
        },
         {
        id: nanoid(),
        title: "Tarea 3",
        createdAt: new Date()
        }
    ]
    },
    {
    id: nanoid(),
    title: "Columna 2",
    tasks: []
    },
      {
    id: nanoid(),
    title: "Columna 3",
    tasks: []
    },
])

</script>

<template>
  <div>
    <div v-for="column in columns" :key="column.id">
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

### Archivo App.vue

- Vamos al archivo **App.vue**
- Modificamos:

```vue
<template>
  <div>
    <trello-board />
  </div>
</template>
```