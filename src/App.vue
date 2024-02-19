<template>
  <div>
    <Header />
    <TaskInput @nuevaTarea="agregarTarea" />
    <TaskList :tareas="tareas" @eliminarTarea="eliminarTarea" @completarTarea="completarTarea" />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Header from './components/Header.vue'
import TaskInput from './components/TaskInput.vue'
import TaskList from './components/TaskList.vue'

const tareas = ref([])

const agregarTarea = nuevaTarea => {
  tareas.value.push({ nombre: nuevaTarea, completada: false })
}

const eliminarTarea = indice => {
  tareas.value.splice(indice, 1)
}

const completarTarea = indice => {
  const tarea = tareas.value[indice]
  tarea.completada = !tarea.completada
}
</script>
