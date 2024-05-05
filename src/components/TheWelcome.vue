<template>
  <div>
    <!-- Elemen input teks -->
    <input type="text" v-model="inputText" @input="handleInput" :class="{ 'red-text': inputText.length > 10 }" :style="{ 'font-weight': inputText.length > 10 ? 'bold' : 'normal' }">
    <p v-if="inputText.length > 0">Tulisan Anda: {{ inputText }}</p>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

// Mendefinisikan variabel reaktif untuk menyimpan nilai input teks
const inputText = ref('');

// Event handler untuk memperbarui nilai inputText saat input diubah
const handleInput = (event) => {
  inputText.value = event.target.value;
};
</script>

<style scoped>
.red-text {
  color: red;
}
</style>