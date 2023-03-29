<script setup>
import ref from 'vue'

const props = defineProps({
  imageURL: String,
  imageAlt: String
})
</script>

<template>
  <img src="{{ imageURL }}" alt="{{ imageAlt }}" />
</template>
