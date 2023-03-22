<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'
import CartButton from './components/CartButton.vue'

let msg = 0
function testClick() {
  msg++
  console.log(msg)
}
</script>

<template>
  <h1>This is a test</h1>
  <CartButton :labelText="msg" @click="testClick()" />
  <RouterView />
</template>

<style scoped></style>
