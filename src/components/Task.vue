<template>
    <ul>
      <li v-for="(tarea, indice) in tareas" :key="indice">
        <TareaIndividual :tarea="tarea" :indice="indice" @eliminarTarea="eliminarTarea" />
      </li>
    </ul>
  </template>
  
  <script setup>
  import { defineProps, emit } from 'vue';
  import TareaIndividual from './List.vue';
  
  const props = defineProps({
    tareas: Array
  });
  
  const eliminarTarea = (indice) => {
    emit('eliminarTarea', indice); 
  };
  </script>
  