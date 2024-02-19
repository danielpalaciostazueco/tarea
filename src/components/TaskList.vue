<template>
  <div>
    <ul>
      <li v-for="(tarea, indice) in tareas" :key="tarea.nombre">
        <TaskDisplay :tarea="tarea" :indice="indice" @eliminarTarea="$emit('eliminarTarea', indice)" @completarTarea="$emit('completarTarea', indice)" />
      </li>
    </ul>
  </div>
</template>

<script setup>
import { defineProps } from 'vue'
import TaskDisplay from './TaskDisplay.vue'

const props = defineProps({
  tareas: Array
})
</script>
