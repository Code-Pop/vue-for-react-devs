<script>
import ProductDisplay from '@/components/ProductDisplay.vue'

export default({
  components: { ProductDisplay },
  data() {
    return {
      cart: [],
      premium: true
    }
  },
  mounted() {
    fetch('http://localhost:3000/cart')
      .then(resp => resp.json())
      .then(data => this.cart = data.content)
  },
  methods: {
    updateCart(id) {
      this.cart.push(id)
    }
  }
})
</script>
  
<template>
  <div class="nav-bar"></div>
  <div class="cart">Cart({{ cart.length }})</div>
  <ProductDisplay :premium="premium" @add-to-cart="updateCart"></ProductDisplay>
</template>