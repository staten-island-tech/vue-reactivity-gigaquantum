<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'
import CartButton from './components/CartButton.vue'
// import CarCard from './components/CarCard.vue'

const carClassColors = ref({
  s2: 'rgb(21, 103, 214)',
  s1: 'rgb(189, 94, 228)',
  a: 'rgb(252, 53, 90)',
  b: 'rgb(255, 101, 51)',
  c: 'rgb(246, 191, 49)',
  d: 'rgb(61, 186, 234)'
})

const carList = ref([
  {
    brandName: 'Land Rover',
    modelName: '110 X',
    year: 2020,
    creditCost: 0,
    imgURL: 'https://www.gtplanet.net/wp-content/uploads/2021/08/fh5-carlist-defender-20210831.jpg',
    inCart: false
  },
  {
    brandName: 'Jaguar',
    modelName: 'Sport XJR-15',
    year: 1991,
    creditCost: 0,
    imgURL: 'https://www.gtplanet.net/wp-content/uploads/2021/08/fh5-carlist-jaguar-20210831.jpg',
    inCart: false
  },
  {
    brandName: 'Hoonigan',
    modelName: "Ford Escort RS Cosworth WRC 'Cossie V2'",
    year: 1994,
    creditCost: 0,
    imgURL: 'https://www.gtplanet.net/wp-content/uploads/2021/08/fh5-carlist-hoonigan-20210831.jpg',
    inCart: false
  },
  {
    brandName: 'Ford',
    modelName: "#25 'Brocky' Ultra4 Bronco RTR",
    year: 2017,
    creditCost: 0,
    imgURL:
      'https://www.gtplanet.net/wp-content/uploads/2021/08/fh5-newfords-broncortr-20210825.jpg',
    inCart: false
  },
  {
    brandName: 'Ford',
    modelName: 'Bronco',
    year: 2021,
    creditCost: 0,
    imgURL: 'https://www.gtplanet.net/wp-content/uploads/2021/08/fh5-newfords-bronco-20210825.jpg',
    inCart: false
  },
  {
    brandName: 'Ford',
    modelName: '#2069 Ford Performance Bronco R',
    year: 2020,
    creditCost: 0,
    imgURL: 'https://www.gtplanet.net/wp-content/uploads/2021/08/fh5-newfords-broncor-20210825.jpg',
    inCart: false
  },
  {
    brandName: 'Ford',
    modelName: 'Racing Escort MK1',
    year: 1967,
    creditCost: 0,
    imgURL: 'https://www.gtplanet.net/wp-content/uploads/2021/08/fh5-newfords-escort-20210825.jpg',
    inCart: false
  },
  {
    brandName: 'Ford',
    modelName: 'Super Duty F-450 DRW Platinum',
    year: 2020,
    creditCost: 0,
    imgURL: 'https://www.gtplanet.net/wp-content/uploads/2021/08/fh5-newfords-f450-20210825.jpg',
    inCart: false
  },
  {
    brandName: 'Porsche',
    modelName: "#65 Rothsport Racing 911 'Desert Flyer'",
    year: 1989,
    creditCost: 0,
    imgURL: 'https://www.gtplanet.net/forza-horizon-5-porsche-list-20210903/',
    inCart: false
  },
  {
    brandName: 'Porsche',
    modelName: 'Macan Rally Raid',
    year: 2018,
    creditCost: 0,
    imgURL:
      'https://www.gtplanet.net/wp-content/uploads/2021/09/fh5-carlist-porsche-964desert-20210903.jpg',
    inCart: false
  },
  {
    brandName: 'Porsche',
    modelName: 'Taycan Turbo S',
    year: 2020,
    creditCost: 0,
    imgURL:
      'https://www.gtplanet.net/wp-content/uploads/2021/09/fh5-carlist-porsche-taycan-20210903.jpg',
    inCart: false
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
  <h1>This is a test</h1>
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
</style>
