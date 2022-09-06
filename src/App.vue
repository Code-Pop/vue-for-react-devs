<script>
export default {
  data() {
    return {
      product: 'Socks'
    }
  },
  created() {
    setTimeout(() => {
      this.product = "New Socks"
    }, 1000)
  }
}
</script>

<template>
  <h1>{{ product }}</h1>
</template>