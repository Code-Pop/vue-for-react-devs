<script setup>
import { ref } from 'vue'

const text = ref('');

const handleInput = (event) => {
  text.value = event.target.value
}
</script>

<template>
  <input :value="text" @input="handleInput" />
  <p>{{ text }}</p>
</template>