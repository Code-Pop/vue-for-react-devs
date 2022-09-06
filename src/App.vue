<script setup>
import { ref } from 'vue'

const useChangeWithDelay = function(state, newVal, delay) {
  setTimeout(() => {
    state.value = newVal
  }, delay)
}

const product = ref('Socks')
  
useChangeWithDelay(product, 'New Socks', 1000)

</script>

<template>
  <h1>{{ product }}</h1>
</template>