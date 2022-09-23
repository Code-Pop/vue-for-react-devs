<script setup>
import { ref } from 'vue'
import ProductDisplay from '@/components/ProductDisplay.vue'
import useCart from '@/composables/useCart.js'

const { cartCount, updateCart } = useCart()
const premium = ref(true)

</script>
  
<template>
  <div class="nav-bar"></div>
  <div class="cart">Cart({{ cartCount }})</div>
  <ProductDisplay :premium="premium" @add-to-cart="updateCart"></ProductDisplay>
</template>