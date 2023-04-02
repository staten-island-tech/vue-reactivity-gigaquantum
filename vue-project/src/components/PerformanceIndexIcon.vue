<script setup>
const props = defineProps({
  carClass: String,
  performanceIndex: Number,
  classColor: String
})

console.log(props.classColor)
</script>

<template>
  <div class="performance-class-icon">
    <p class="class-text">{{ carClass }}</p>
    <p class="performance-index-text">{{ performanceIndex }}</p>
  </div>
</template>

<style scoped>
.performance-class-icon {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  border-color: white;
  border-style: solid;
  border-width: 0.5rem;
  background-color: v-bind(classColor);
}

p {
  font-size: 3.5rem;
}

.class-text {
  background-color: v-bind(classColor);
  width: 4.5rem;
  height: 4.5rem;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 600;
}

.performance-index-text {
  background-color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 600;
  width: 7rem;
  height: 4.5rem;
}
</style>
