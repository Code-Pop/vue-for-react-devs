<script setup>
import { ref, onMounted, computed } from 'vue'
import ProductDisplay from '@/components/ProductDisplay.vue'

function useCart () {
  const cart = ref([])
  const cartCount = computed(() => cart.value.length)

  onMounted(() => {
    fetch('http://localhost:3000/cart')
      .then(resp => resp.json())
      .then(data => cart.value = data.content)
  })

  const updateCart = (id) => {
    cart.value.push(id)
  }

  return { cartCount, updateCart }
}

const { cartCount, updateCart } = useCart()
const premium = ref(true)

</script>
  
<template>
  <div class="nav-bar"></div>
  <div class="cart">Cart({{ cartCount }})</div>
  <ProductDisplay :premium="premium" @add-to-cart="updateCart"></ProductDisplay>
</template>