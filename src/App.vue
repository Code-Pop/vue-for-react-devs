<script setup>
import { ref } from 'vue'
import socksGreenImage from '@/assets/images/socks_green.jpg'

const product = ref('Socks')

</script>

<template>
  <div class="product-display">
    <div class="product-container">
      <div class="product-image">
        <img v-bind:src="socksGreenImage">
      </div>
      <div class="product-info">
        <h1>{{ product }}</h1>
      </div>
    </div>
  </div>
</template>