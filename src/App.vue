<script>
import { ref } from 'vue'

export default {
  setup() {
    const product = ref('Socks')

    setTimeout(() => {
      product.value = "New Socks"
    }, 1000)

    return { product }
  }
}
</script>

<template>
  <h1>{{ product }}</h1>
</template>