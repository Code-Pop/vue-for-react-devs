<script setup>
import { ref } from 'vue'
import socksGreenImage from './assets/images/socks_green.jpeg'

const product = ref('Socks')
const image = ref(socksGreenImage)

</script>
  
<template>
  <div class="nav-bar"></div>
  <div class="product-display">
    <div class="product-container">
      <div class="product-image">    
        <img v-bind:src="image">
      </div>
      <div class="product-info">
        <h1>{{ product }}</h1>
      </div>
    </div>
  </div>
</template>