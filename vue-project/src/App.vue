<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'
import CartButton from './components/CartButton.vue'

const msg = ref(1)
function testClick() {
  msg.value++
  console.log(msg.value)
}
</script>

<template>
  <h1>This is a test</h1>
  <CartButton :labelText="msg" @click="testClick()" />
  <RouterView />
</template>

<style scoped></style>
