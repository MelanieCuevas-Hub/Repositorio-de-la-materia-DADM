<template>
    <div @click="selectPlan" class="plan">
      <div class="description">
        <span class="title">
          {{ name }} {{ selected ? '🌟' : ''}}
        </span>
      </div>
    </div>
  </template>
  
  <script setup> 
// IMPORT ref FUNCTION
import { ref } from 'vue';

  // Usando macro para definir las props
  const props = defineProps({
    name: {
      type: String,
      required: true
    }
  });
  // DEFINE EVENT
  const emit = defineEmits(['select']);
  // VARIABLE QUE PERMITE RECORDAR SI EL PLAN A SIDO SELECCIONADO
  const selected = ref(false);
  //FUNCION QUE PERMITE CAMBIAR EL ESTADO DE LA VARIABLE
  const selectPlan = () => {
  selected.value = true;
  //EMITE EVENTO DE QUE EL PLAN HA SIDO SELECCIONADO
  emit('select', props.name);
};
  </script>
  
  <style scoped>
  /* Agrega tus estilos aquí */
  </style>