<template>
  <div>
    <input v-model="nuevaTarea" placeholder="Introduce el nombre de la tarea" />
    <button @click="emitirTarea">Añadir Tarea</button>
  </div>
</template>

<script setup>
import { ref, defineEmits } from 'vue'

const nuevaTarea = ref('')
const emit = defineEmits(['nuevaTarea'])

const emitirTarea = () => {
  if (nuevaTarea.value.trim()) {
    emit('nuevaTarea', nuevaTarea.value)
    nuevaTarea.value = ''
  }
}
</script>
