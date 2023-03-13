<script setup>
import { ref } from 'vue'
// import { RouterLink, RouterView } from 'vue-router'
import { PartCard } from './components/PartCard.vue'

const test = ref('this is a test!')
</script>

<template>
  <PartCard>{{ test }}</PartCard>
</template>
