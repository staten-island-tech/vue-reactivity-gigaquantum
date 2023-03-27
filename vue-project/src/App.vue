<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'
import CartButton from './components/CartButton.vue'
// import CarCard from './components/CarCard.vue'

const carClassInfo = ref({
  s2: {
    name: 'S2',
    maxRating: 998,
    color: 'rgb(21, 103, 214)'
  },
  s1: {name: 'S1', maxRating: 900,
  color: 'rgb(189, 94, 228)'},
  a: {name: 'A',maxRating: 800,
  color: 'rgb(252, 53, 90)'},
  b: {name: 'B', maxRating: 700, color: 'rgb(255, 101, 51)'},
  c: {name: 'C', maxRating: 600, color: 'rgb(246, 191, 49)'},
  d: {name: 'D', maxRating: 500, color: 'rgb(61, 186, 234)'}
})


const carList = ref([
  {
    brandName: 'Land Rover',
    modelName: '110 X',
    year: 2020,
    creditCost: 80000,
    imgURL: 'https://www.gtplanet.net/wp-content/uploads/2021/08/fh5-carlist-defender-20210831.jpg',
    inCart: false,
    performanceIndex: 534
  },
  {
    brandName: 'Jaguar',
    modelName: 'Sport XJR-15',
    year: 1991,
    creditCost: 500000,
    imgURL: 'https://www.gtplanet.net/wp-content/uploads/2021/08/fh5-carlist-jaguar-20210831.jpg',
    inCart: false,
    performanceIndex: 828
  },
  {
    brandName: 'Hoonigan',
    modelName: "Ford Escort RS Cosworth WRC 'Cossie V2'",
    year: 1994,
    creditCost: 500000,
    imgURL: 'https://www.gtplanet.net/wp-content/uploads/2021/08/fh5-carlist-hoonigan-20210831.jpg',
    inCart: false,
    performanceIndex: 783
  },
  {
    brandName: 'Ford',
    modelName: "#25 'Brocky' Ultra4 Bronco RTR",
    year: 2017,
    creditCost: 500000,
    imgURL:
      'https://www.gtplanet.net/wp-content/uploads/2021/08/fh5-newfords-broncortr-20210825.jpg',
    inCart: false,
    performanceIndex: 748
  },
  {
    brandName: 'Ford',
    modelName: 'Bronco',
    year: 2021,
    creditCost: 55000,
    imgURL: 'https://www.gtplanet.net/wp-content/uploads/2021/08/fh5-newfords-bronco-20210825.jpg',
    inCart: false,
    performanceIndex: 560
  },
  {
    brandName: 'Ford',
    modelName: '#2069 Ford Performance Bronco R',
    year: 2020,
    creditCost: 0,
    imgURL: 'https://www.gtplanet.net/wp-content/uploads/2021/08/fh5-newfords-broncor-20210825.jpg',
    inCart: false,
    performanceIndex: 544
  },
  {
    brandName: 'Ford',
    modelName: 'Racing Escort MK1',
    year: 1967,
    creditCost: 500000,
    imgURL: 'https://www.gtplanet.net/wp-content/uploads/2021/08/fh5-newfords-escort-20210825.jpg',
    inCart: false,
    performanceIndex: 636
  },
  {
    brandName: 'Ford',
    modelName: 'Super Duty F-450 DRW Platinum',
    year: 2020,
    creditCost: 70000,
    imgURL: 'https://www.gtplanet.net/wp-content/uploads/2021/08/fh5-newfords-f450-20210825.jpg',
    inCart: false,
    performanceIndex: 466
  },
  {
    brandName: 'Porsche',
    modelName: "#65 Rothsport Racing 911 'Desert Flyer'",
    year: 1989,
    creditCost: 500000,
    imgURL:
      'https://www.gtplanet.net/wp-content/uploads/2021/09/fh5-carlist-porsche-964desert-20210903-800x450.jpg',
    inCart: false,
    performanceIndex: 694
  },
  {
    brandName: 'Porsche',
    modelName: 'Macan Rally Raid',
    year: 2018,
    creditCost: 250000,
    imgURL:
      'https://www.gtplanet.net/wp-content/uploads/2021/09/fh5-carlist-porsche-macanrr-20210903-800x450.jpg',
    inCart: false,
    performanceIndex: 637
  },
  {
    brandName: 'Porsche',
    modelName: 'Taycan Turbo S',
    year: 2020,
    creditCost: 185000,
    imgURL:
      'https://www.gtplanet.net/wp-content/uploads/2021/09/fh5-carlist-porsche-taycan-20210903.jpg',
    inCart: false,
    performanceIndex: 807
  }
])

const bool = ref(false)
const selectedMsg = ref('IN CART')
const defaultMsg = ref('ADD TO CART')

function toggleBool() {
  bool.value = !bool.value
}
</script>

<template>
  <h1>carz</h1>
  <img
    src="https://www.gtplanet.net/wp-content/uploads/2021/09/fh5-carlist-porsche-taycan-20210903.jpg"
    alt="taycan turbo s 2020"
  />
  <CartButton
    :defaultText="defaultMsg"
    :selectedText="selectedMsg"
    :selectedStatus="bool"
    @click="toggleBool()"
  />
  <!-- <CarCard /> -->
  <RouterView />
</template>

<style scoped>
h1 {
  font-size: 2rem;
}

img {
  width: 40rem;
}
</style>
