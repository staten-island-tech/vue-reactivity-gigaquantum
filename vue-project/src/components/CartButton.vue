<script setup>
const props = defineProps({
  defaultText: String,
  selectedText: String,
  selectedStatus: Boolean
})
</script>

<template>
  <button class="selected-btn" v-if="selectedStatus">{{ selectedText }}</button>
  <button class="default-btn" v-else>{{ defaultText }}</button>
</template>

<style scoped>
button {
  border-width: 0;
  width: 13rem;
  height: 3.5rem;
  margin: 1rem;
  border-radius: 0.75rem;
  font-size: 2.25rem;
  font-weight: 700;
  /* letter-spacing: 0.01rem; */
  border-style: solid;
  border-color: white;
  border-width: 0.5rem;
}
button:hover {
  outline-color: white;
  outline-style: solid;
  outline-offset: 0.5rem;
  outline-width: 0.5rem;
}

.selected-btn {
  color: rgb(0, 0, 0);
  background-color: rgb(255, 255, 255);
}
.default-btn {
  color: rgb(255, 255, 255);
  background-color: rgba(0, 0, 0);
}
</style>
