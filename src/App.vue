<script setup>
import { ref, onMounted, computed, watch } from 'vue'
import ProductDisplay from '@/components/ProductDisplay.vue'

function useCart () {
  const cart = ref(null)

  const cartCount = computed(() => {
    if (cart.value === null) {
      return 0
    }
    else {
      return cart.value.length
    }
  })

  onMounted(() => {
    fetch('http://localhost:3000/cart')
      .then(resp => resp.json())
      .then(data => cart.value = data.content)
  })

  watch(cart, (value, oldValue) => {
    if(oldValue === null) return

    fetch('http://localhost:3000/cart', {
      method: 'PUT',
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({
        content: value
      })
    })
  })

  const updateCart = (id) => {
    cart.value = cart.value.concat(id)
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