
<script setup>
import planItem from './components/plan-item.vue';
</script>

<template>
  <header>
    <div style="text-align:">
      <span id="logo">ITGAM BOX EXP</span> <br>
      <img src="./assets/logo.png" alt="logo">
    </div>
  </header>

  <div class="content">
    <h1 class="title">Coffee Plans</h1>

    <h2 class="subtitle">
      Viajamos por el mundo para encontrar el mejor café de origen único para ti
    </h2>

    <div class="plans">
      <planItem>El Soltero</planItem>
      <planItem>El Curioso</planItem>
      <planItem>El Adicto</planItem>
      </div>
  </div>
      
</template>

<style scoped>
</style>
