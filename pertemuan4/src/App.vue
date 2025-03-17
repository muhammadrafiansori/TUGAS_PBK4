<script setup>
import { ref } from 'vue';

//Variabel Reaktif dengan ref()
const counter = ref(0);
const incrementCounter = () => {
  counter.value++;
};

//Text Interpolation
const username = ref("Rafi");

//v-model Binding
const userInput = ref("");

//Event Listener
const message = ref("Klik tombol untuk mengubah teks!");
const updateMessage = () => {
  message.value = "Teks telah berubah!";
};

// Attribute Binding (v-bind)
const websiteUrl = ref("https://vuejs.org");
const imageUrl = ref("https://image.web.id/images/7cb22a8a9885468d96662f6ece61ceb2bc95666d-500x300.png");
const isDisabled = ref(true);
const attributes = ref()

//Conditional Rendering (v-if, v-show)
const isVisible = ref(true);
</script>

<template>
  <!-- Attribute Binding -->
  <h1 v-bind="attributes">Hello Vue!</h1>
  <a :href="websiteUrl">Kunjungi Vue.js</a>
  <img :src="imageUrl" alt="Gambar Dinamis" />

  <!-- Conditional Rendering -->
  <button @click="isVisible = !isVisible">Toggle</button>
  <p v-if="isVisible">Teks ini bisa muncul dan menghilang.</p>


  <!-- Event Listener -->
  <p>{{ message }}</p>
  <button @click="updateMessage">Klik Saya</button>

  <!-- Text Interpolation -->
  <p>Halo, {{ username }}!</p>

  <!-- v-model Binding -->
  <input v-model="userInput" placeholder="Masukkan Nama" />
  <p>Hallo ,{{ userInput }}</p>

  <!-- Variabel Reaktif dengan ref() -->
  <p>Counter: {{ counter }}</p>
  <button @click="incrementCounter">Tambah</button>
</template>

<style>
</style>
