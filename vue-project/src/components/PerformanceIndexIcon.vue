<script setup>
const props = defineProps({
  carClass: String,
  performanceIndex: Number,
  classColor: String
})
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
  border-width: 0.375rem;
  background-color: v-bind(classColor);
  margin: 1rem;
}

p {
  font-size: 2.75rem;
}

.class-text {
  background-color: v-bind(classColor);
  width: 3.5rem;
  height: 3.5rem;
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
  width: 5.5rem;
  height: 3.5rem;
}
</style>
