<script setup>
import { useSlots } from 'vue'

defineProps({
  reviews: {
    type: Array,
    required: true
  }
})
</script>

<template>
  <div class="review-container">
    <h3><slot name="heading"></slot></h3>
    <ul>
      <li v-for="(review, index) in reviews" :key="index">
        <slot name="item" :review="review">
          <span>{{ review.name }}</span>: <span>{{ review.content }}</span>
        </slot>
      </li>
    </ul>
  </div>
</template>