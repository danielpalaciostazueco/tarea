<template>
    <div>
      <span :class="{'tarea-completada': tarea.completada}">
        {{ tarea.nombre }}
      </span>
      <button @click="marcarComoCompletada">Completada</button>
      <button @click="eliminar">Eliminar</button>
    </div>
  </template>
  
  <script setup>
  import { defineProps, emit } from 'vue';
  
  const props = defineProps({
    tarea: Object,
    indice: Number
  });
  
  const marcarComoCompletada = () => {
    // Este método solo cambiaría el estilo o estado visualmente, pero no modificará la lista en el padre
    props.tarea.completada = !props.tarea.completada;
  };
  
  const eliminar = () => {
    emit('eliminarTarea', props.indice); // Emitir evento hacia ListaTareas, que a su vez lo emitirá al padre
  };
  </script>
  
  <style>
  .tarea-completada {
    text-decoration: line-through;
  }
  </style>
  