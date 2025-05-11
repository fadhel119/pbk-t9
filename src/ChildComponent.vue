<template>
    <div class="child">
      <h3>Komponen Anak</h3>
      <p><strong>Pesan dari Induk:</strong> {{ pesan }}</p>
      
      <button @click="kirimPerbaruan">Kirim Perubahan ke Komponen Induk</button>
  
      <div class="slots">
        <!-- Slot Default -->
        <slot></slot>
        <!-- Named Slot -->
        <slot name="footer"></slot>
      </div>
    </div>
  </template>
  
  <script setup>
  const props = defineProps({
    pesan: {
      type: String,
      required: true,
    },
  });
  
  const emit = defineEmits(['perbarui-pesan']);
  
  const kirimPerbaruan = () => {
    emit('perbarui-pesan', 'Pesan diperbarui dari Komponen Anak!');
  };
  </script>
  
  <style scoped>
  .child {
    padding: 10px;
    margin-top: 10px;
    border: 2px dashed #666;
  }
  
  button {
    margin-bottom: 10px;
    padding: 5px 10px;
    cursor: pointer;
  }
  
  .slots {
    background-color: #f9f9f9;
    padding: 10px;
    margin-top: 10px;
    border: 1px solid #ccc;
  }
  </style>
  