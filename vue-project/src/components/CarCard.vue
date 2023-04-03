<script setup>
// import { ref } from 'vue'
import CartButton from './CartButton.vue'
import PerformanceIndexIcon from './PerformanceIndexIcon.vue'
import CarImage from './CarImage.vue'

const props = defineProps({
  carCost: Number,
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
    <div class="car-name-info">
      <h2>
        <span class="model-name">{{ carModelName }}</span>
        <span class="seperator-space">&nbsp;</span>
        <span class="car-year">{{ carYear }}</span>
      </h2>
      <h3 class="brand-name">{{ carBrandName }}</h3>
    </div>
    <CarImage :imageURL="carImageURL" :imageAlt="carImageAlt" />
    <div class="car-stat-info">
      <h3 class="car-cost">CR {{ carCost }}</h3>
      <PerformanceIndexIcon
        class="performance-icon"
        :carClass="carClassName"
        :performanceIndex="carPerformanceIndex"
        :classColor="classColor"
      />
    </div>

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
  font-size: 5rem;
  color: black;
  margin: 0;
  padding: 0;
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

.car-name-info {
  display: flex;
  flex-direction: column;
  text-align: center;
  background-color: rgb(246, 247, 249);
  width: 37.5rem;
  padding-left: 1.5rem;
  padding-right: 1.5rem;
}

.car-stat-info {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  width: 37.5rem;
}

.car-cost {
  background-color: v-bind(classColor);
  color: white;
  border-color: white;
  border-style: solid;
  border-width: 0.375rem;
  font-size: 2.5rem;
  width: fit-content;
  height: fit-content;
  margin: 1rem;
  padding: 0.25rem;
  font-weight: 600;
}

.performance-icon {
}
.brand-name {
  font-size: 2.5rem;
  font-weight: 350;
}
.model-name {
  font-weight: 750;
}
.car-year {
  font-weight: 350;
}
.seperator-space {
  font-size: 2.5rem;
}
</style>
