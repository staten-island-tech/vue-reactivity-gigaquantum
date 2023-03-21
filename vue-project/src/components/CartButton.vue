<script setup>
const props = defineProps({
  labelText: String
})
</script>

<template>
  <button>
    {{ labelText }}
  </button>
</template>

<style scoped>
button {
  font-size: 5%;
  color: blueviolet;
}
</style>
