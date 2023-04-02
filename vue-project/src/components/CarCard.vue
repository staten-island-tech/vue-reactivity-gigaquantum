<script setup>
// import { ref } from 'vue'
import CartButton from './CartButton.vue'
import PerformanceIndexIcon from './PerformanceIndexIcon.vue'
import CarImage from './CarImage.vue'

const props = defineProps({
  carYear: Number,
  carBrandName: String,
  carModelName: String,
  carImageURL: String,
  carImageAlt: String,
  carClassName: String,
  carPerformanceIndex: Number,
  classColor: String,
  btnDefaultText: String,
  btnSelectedText: String,
  cartSelectedStatus: Boolean
})

// const emit = defineEmits(['cartStatusChanged'])
</script>

<template>
  <div class="car-card">
    <CarImage :imageURL="carImageURL" :imageAlt="carImageAlt" />
    <PerformanceIndexIcon
      :carClass="carClassName"
      :performanceIndex="carPerformanceIndex"
      :classColor="classColor"
    />
    <h2>{{ carBrandName }}</h2>
    <h2>{{ carModelName }}</h2>
    <h2>{{ carYear }}</h2>
    <CartButton
      :defaultText="btnDefaultText"
      :selectedText="btnSelectedText"
      :selectedStatus="cartSelectedStatus"
      :buttonBackgroundColor="classColor"
      @click="$emit('response')"
    />
  </div>
</template>

<style scoped>
h2 {
  font-size: 3rem;
  color: white;
}
img {
  /* width: 40rem; */
}
.car-card {
  background-color: v-bind(classColor);
  /* border-color: blueviolet;
  border-style: solid;
  border-width: 0.25rem; */
  width: min-content;
  height: fit-content;
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  align-items: center;
  margin: 1rem;
}
</style>
