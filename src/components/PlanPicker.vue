<script setup>
 import PlanPickerItem from './PlanPickerItem.vue';
 import { ref } from 'vue';
 // CREANDO UNA REFERENCIA REACTIVA PARA ALAMQCENAR EL PLAN SELECCIONADO
 const selectedPlan =  ref(null)
 const plans =
  ref(['El cafetero','El chelero','El intelectual']);
 const selectPlan = (name) => {
// ALMACENAR EL PLAN SELECCIONADO 
 selectedPlan.value = name;
  }
</script>

<template>
<div class="plans">
  <PlanPickerItem v-for="plan in plans" :key="plan" :name="plan" @select="selectPlan"
  :select-plan="selectedPlan"
  />
</div>
<p> {{ selectedPlan }} </p>
</template>



<style scoped>

</style>