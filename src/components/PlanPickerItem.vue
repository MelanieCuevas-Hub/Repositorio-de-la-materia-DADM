<template>
    <div @click="selectPlan" class="plan">
      <div class="description">
        <span class="title">
          {{ name }} {{ isSelected ? '🌟' : ''}}
        </span>
      </div>
    </div>
  </template>
  
  <script setup>
  // IMPORTAMOS UN MACRO
  import { computed } from 'vue';

  // Usando macro para definir las props
  const props = defineProps({
    name: {
      type: String,
      required: true
    },
    selectPlan: String
  });
  // DEFINE EVENT
  const emit = defineEmits(['select']);
  //FUNCION QUE PERMITE CAMBIAR EL ESTADO DE LA VARIABLE
  const selectPlan = () => {
  //EMITE EVENTO DE QUE EL PLAN HA SIDO SELECCIONADO
  emit('select', props.name);
};
//CREANDO UNA PROPIEDAD COMPUTADA 
//PARA SABER SI EL ´PLAN A SIDO SELECCIONADO
const isSelected = computed(() => { 
   return props.name === props.selectPlan;

})
  </script>
  
  <style scoped>
  /* Agrega tus estilos aquí */
  </style>