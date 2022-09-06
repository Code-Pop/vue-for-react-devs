<script setup>
import { ref } from 'vue'

const product = ref('Socks')
  

setTimeout(() => {
  product.value = "New Socks"
}, 1000)

</script>

<template>
  <h1>{{ product }}</h1>
</template>