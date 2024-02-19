<template>
  <div>
    <span :class="{'tarea-completada': tarea.completada}">
      {{ tarea.nombre }}
    </span>
    <button @click="$emit('completarTarea')">Completar</button>
    <button @click="$emit('eliminarTarea')">Eliminar</button>
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue'

const props = defineProps({
  tarea: Object,
  indice: Number
})
const emit = defineEmits(['eliminarTarea', 'completarTarea'])
</script>

<style>
.tarea-completada {
  text-decoration: line-through;
}
</style>
