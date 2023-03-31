<script setup>
const props = defineProps({
  carClass: String,
  performanceIndex: Number,
  classColor: String
})

console.log(props.carClass)
</script>

<template>
  <p>{{ carClass }}</p>
  <p>{{ performanceIndex }}</p>
</template>

<style scoped>
template {
  font-size: 4rem;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  border-color: white;
  border-style: solid;
  border-width: 0.25rem;
  background-color: v-bind(classColor);
}
</style>
