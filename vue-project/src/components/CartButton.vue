<script setup>
const props = defineProps({
  labelText: Number
})
</script>

<template>
  <button>
    {{ labelText }}
  </button>
</template>

<style scoped>
button {
  font-size: 20px;
  color: blueviolet;
}
</style>
