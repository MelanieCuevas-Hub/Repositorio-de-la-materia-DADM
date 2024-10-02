<script setup>
import { ref } from 'vue';
const header = ref('App Lista de compras');
//---items---
//Item.Model
const items = ref([
  {id: 1, label: '10 bolillos'},
  {id: 2, label: '1 lata de frijoles'},
  {id: 3, label: '1 lata de atún'},
  {id: 4, label: '1 Nutella'}
]);

// Items-Method
const saveItem = (item) => {
  items.value.push({id: items.value.length + 1, label: newItem.value});
//Clean the input
  newItem.value = '';

}


const newItem = ref('');
const newItemHighPriority = ref(false);
</script>

<template>
  <h1> <i class="material-icons shopping-cart-icon">local_mall</i> {{ header }}</h1>
  <!-- Agrupando Entradas de usuario -->
  <form 
  class="add-item form" 
  v-on:submit.prevent="saveItem">
    <!-- Entrada de texto -->
    <input 
      type="text" 
      placeholder="Add Item" 
      v-model.trim="newItem">
    <!-- Radio Buttons -->
    <label><input type="checkbox" v-model="newItemHighPriority">Alta Prioridad</label>
    <!-- Boton -->
    <button 
      class="btn btn-primary">
      Salvar Articulo
    </button>
  </form>
  <!-- Lista -->
  <ul>
    <li v-for="{ id, label } in items" v-bind:key="id">
      🛍️ {{ label }}
    </li>
  </ul>
</template>

<style scoped>
.shopping-cart-icon {
  font-size: 2rem; /* Adjust the font-size value as per your desired size */
}
</style>