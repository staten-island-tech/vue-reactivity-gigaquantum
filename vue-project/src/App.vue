<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'
import { carClassInfo, getCarClass, carClassList } from './data.js'
import CartButton from './components/CartButton.vue'
import performanceIndexIcon from './components/PerformanceIndexIcon.vue'

const selectedMsg = ref('IN CART')
const defaultMsg = ref('ADD TO CART')

function toggleBool() {}
</script>

<template>
  <div class="car-card" v-for="car in carList">
    <img
      :src="car.imgURL"
      alt="Image of a {{ car.year }} {{ car.brandName }} {{ car.modelName }}"
    />
    <performanceIndexIcon />
    <sub class="performance-index-icon"> </sub>
    <h2>{{ car.brandName }}</h2>
    <h2>{{ car.modelName }}</h2>
    <h2>{{ car.year }}</h2>
    <CartButton
      :defaultText="defaultMsg"
      :selectedText="selectedMsg"
      :selectedStatus="car.inCart"
      :buttonBackgroundColor="[getCarClass(car.performanceIndex)].color"
      @click="car.inCart = !car.inCart"
    />
  </div>

  <!-- <CarCard /> -->
  <RouterView />
</template>

<style scoped>
h1 {
  font-size: 2rem;
}

h2 {
  font-size: 3rem;
}

img {
  width: 40rem;
}
.car-card {
  border-color: blueviolet;
  border-style: solid;
  border-width: 0.25rem;
  width: fit-content;
  height: fit-content;
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  align-items: center;
}
</style>
