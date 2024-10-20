<template>
  <div :class="currentTheme" id="app-container">
    <div class="header">
      <h1>{{ title }}</h1>
      <p>{{ description }}</p>
    </div>
    
    <div class="theme-selector">
      <p></p>
      <button v-for="theme in themes" :key="theme" @click="changeTheme(theme)">
        {{ theme }}
      </button>
    </div>
    
    <div class="message-box">
      <p class="message">{{ message }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

// Data untuk aplikasi
const title = 'ini aplikasi coba-coba ganti theme'
const message = ref('pilih tema yg kalian mau untuk diterapkan di frame')
const themes = ['Default', 'Dark', 'Light', 'Ocean', 'Forest']

// Data reaktif untuk tema
const currentTheme = ref('Default')

// Fungsi untuk mengubah tema
function changeTheme(theme) {
  currentTheme.value = theme
}
</script>

<style scoped>
/* Gaya dasar */
#app-container {
  text-align: center;
  max-width: 600px;
  margin: 50px auto;
  padding: 20px;
  border-radius: 10px;
  transition: background-color 0.5s ease, color 0.5s ease;
}

.header {
  margin-bottom: 20px;
}

h1 {
  font-size: 2.5rem;
  margin-bottom: 10px;
}

p {
  font-size: 1.2rem;
}

.theme-selector {
  margin-bottom: 20px;
}

button {
  padding: 10px 20px;
  font-size: 1rem;
  margin-right: 10px;
  cursor: pointer;
  border: none;
  border-radius: 5px;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #ddd;
}

.message-box {
  padding: 20px;
  border-radius: 10px;
}

/* Tema "Default" */
.Default {
  background-color: #f9f9f9;
  color: #333;
}

.Default .message-box {
  background-color: #fff;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

/* Tema "Dark" */
.Dark {
  background-color: #2c3e50;
  color: #ecf0f1;
}

.Dark .message-box {
  background-color: #34495e;
}

/* Tema "Light" */
.Light {
  background-color: #f0f4f8;
  color: #333;
}

.Light .message-box {
  background-color: #fff;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

/* Tema "Ocean" */
.Ocean {
  background-color: #0077b6;
  color: #caf0f8;
}

.Ocean .message-box {
  background-color: #90e0ef;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

/* Tema "Forest" */
.Forest {
  background-color: #2d6a4f;
  color: #d8f3dc;
}

.Forest .message-box {
  background-color: #52b788;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}
</style>
