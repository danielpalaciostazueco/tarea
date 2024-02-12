<template>
    <div>
      <input v-model="nuevaTarea" placeholder="Introduce el nombre de la tarea" />
      <button @click="enviarTarea">Añadir Tarea</button>
      <ListaTareas :tareas="tareas" @eliminarTarea="eliminarTarea" />
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import ListaTareas from './Netlink.vue';
  
  const nuevaTarea = ref('');
  const tareas = ref([]);
  
  const enviarTarea = () => {
    if (nuevaTarea.value.trim()) {
      tareas.value.push({ nombre: nuevaTarea.value, completada: false });
      nuevaTarea.value = '';
    }
  };
  
  const eliminarTarea = (indice) => {
    tareas.value.splice(indice, 1); 
  };
  </script>
  