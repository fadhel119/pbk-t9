<template>
  <div class="app">
    <h1>Relasi Antar Komponen - Vue 3</h1>
    <ParentComponent />
  </div>
</template>

<script setup>
import ParentComponent from './ParentComponent.vue';
</script>

<style>
.app {
  font-family: Arial, sans-serif;
  padding: 20px;
}
</style>
