<script setup>
const props = defineProps({
  imageURL: String,
  imageAlt: String
})
</script>

<template>
  <img :src="imageURL" :alt="imageAlt" />
</template>

<style scoped>
img {
  width: 40rem;
}
</style>
