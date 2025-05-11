<template>
    <div class="parent">
      <h2>Komponen Induk</h2>
      <ChildComponent :pesan="pesanInduk" @perbarui-pesan="tanganiPerbarui">
        <!-- Slot Default -->
        <template #default>
          <p>Ini adalah konten slot default yang dikirim dari komponen induk.</p>
        </template>
  
        <!-- Slot dengan nama: footer -->
        <template #footer>
          <p><strong>Ini footer</strong> dari Komponen Induk menggunakan named slot.</p>
        </template>
      </ChildComponent>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import ChildComponent from './ChildComponent.vue';
  
  const pesanInduk = ref("Pesan awal dari Komponen Induk");
  
  const tanganiPerbarui = (pesanBaru) => {
    pesanInduk.value = pesanBaru;
  };
  </script>
  
  <style scoped>
  .parent {
    padding: 10px;
    border: 2px solid #999;
    margin-top: 10px;
  }
  </style>
  