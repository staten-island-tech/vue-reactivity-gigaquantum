<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'
import CartButton from './components/CartButton.vue'

const msg = ref('click me!')
function testClick(text) {
  console.log(text)
}
</script>

<template>
  <h1>This is a test</h1>
  <CartButton :labelText="msg" @click="testClick('clicked')" />
  <RouterView />
</template>

<style scoped></style>
