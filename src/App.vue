<script setup>
import { reactive } from 'vue'

const product = reactive({
  name: 'Socks'
})

setTimeout(() => {
  product.name = "New Socks"
}, 1000)

</script>

<template>
  <h1>{{ product.name }}</h1>
</template>