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
  padding: 25px;
  margin: 10px;
  border-radius: 15px;
}
button:hover {
  outline-color: aqua;
  outline-style: solid;
  outline-offset: 5px;
  outline-width: 10px;
}
</style>
