<script setup>
import { ref } from 'vue'
import CartButton from './CartButton.vue'

const bool = ref(false)
const selectedMsg = ref('IN CART')
const defaultMsg = ref('ADD TO CART')

function toggleBool() {
  bool.value = !bool.value
}
</script>

<template>
  <p>car</p>
  <CartButton
    :defaultText="defaultMsg"
    :selectedText="selectedMsg"
    :selectedStatus="bool"
    @click="toggleBool()"
  />
</template>

<style scoped>
p {
  font-size: 2rem;
}
</style>
