---
sidebar: auto
---


# Draggable Tareas

## Archivo TrelloBoard.vue

## TrelloBoard.vue

```vue
<template>
  <div >
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
          <draggable
            v-model="column.tasks"
            group="tasks"
            :animation="150"
            item-key="id">
            <template #item="{ element: task }: { element: Task }">
              <TrelloBoardTask
              :task="task" 
              />
          </template>
          </draggable>   
          <footer>
            <button class="text-gray-500">+ Add a Card</button>
          </footer>
        </div>
      </template>
    </draggable> 
  </div>  
</template> 
```
 
 ## Clonar Tareas

```vue
<script>
const shift = useKeyModifier('Shift', { initial: false })

console.log(shift.value)
</script>

<template>
  <div >
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
          <draggable
            v-model="column.tasks"
            :group="{ name: 'tasks', pull: shift ? 'clone' : true }"
            :animation="150"
            handle=".drag-handle"
            item-key="id">
            <template #item="{ element: task }: { element: Task }">
              <TrelloBoardTask
              :task="task" 
              />
          </template>
          </draggable>   
          <footer>
            <button class="text-gray-500">+ Add a Card</button>
          </footer>
        </div>
      </template>
    </draggable> 
  </div>  
</template>

```
