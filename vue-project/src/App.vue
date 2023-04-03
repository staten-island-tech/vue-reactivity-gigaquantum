<script setup>
import { /* RouterLink, */ RouterView } from 'vue-router'
import { ref, computed } from 'vue'
/* import CartButton from './components/CartButton.vue'
import PerformanceIndexIcon from './components/PerformanceIndexIcon.vue'
import CarImage from './components/CarImage.vue' */
import CarCard from './components/CarCard.vue'

const carClassInfo = ref([
  {
    className: 'S2',
    maxRating: 998,
    color: 'rgb(21, 103, 214)'
  },
  { className: 'S1', maxRating: 900, color: 'rgb(189, 94, 228)' },
  { className: 'A', maxRating: 800, color: 'rgb(252, 53, 90)' },
  { className: 'B', maxRating: 700, color: 'rgb(255, 101, 51)' },
  { className: 'C', maxRating: 600, color: 'rgb(246, 191, 49)' },
  { className: 'D', maxRating: 500, color: 'rgb(61, 186, 234)' }
])

function getCarClass(performanceIndex) {
  for (const dataEntry of carClassInfo.value.sort((a, b) => {
    return a.maxRating - b.maxRating
  })) {
    if (dataEntry.maxRating >= performanceIndex) {
      return dataEntry
    }
  }
}

const carList = ref([
  {
    brandName: 'Land Rover',
    modelName: '110 X',
    year: 2020,
    creditCost: 80000,
    imgURL: './vue-project/public/img/fh5-carlist-defender-20210831.jpg',
    inCart: false,
    performanceIndex: 534
  },
  {
    brandName: 'Jaguar',
    modelName: 'Sport XJR-15',
    year: 1991,
    creditCost: 500000,
    imgURL: './vue-project/public/img/fh5-carlist-jaguar-20210831.jpg',
    inCart: false,
    performanceIndex: 828
  },
  {
    brandName: 'Hoonigan',
    modelName: "Ford Escort RS Cosworth WRC 'Cossie V2'",
    year: 1994,
    creditCost: 500000,
    imgURL: './vue-project/public/img/fh5-carlist-hoonigan-20210831.jpg',
    inCart: false,
    performanceIndex: 783
  },
  {
    brandName: 'Ford',
    modelName: "#25 'Brocky' Ultra4 Bronco RTR",
    year: 2017,
    creditCost: 500000,
    imgURL: './vue-project/public/img/fh5-newfords-broncortr-20210825.jpg',
    inCart: false,
    performanceIndex: 748
  },
  {
    brandName: 'Ford',
    modelName: 'Bronco',
    year: 2021,
    creditCost: 55000,
    imgURL: './vue-project/public/img/fh5-newfords-bronco-20210825.jpg',
    inCart: false,
    performanceIndex: 560
  },
  {
    brandName: 'Ford',
    modelName: '#2069 Ford Performance Bronco R',
    year: 2020,
    creditCost: 250000,
    imgURL: './vue-project/public/img/fh5-newfords-broncor-20210825.jpg',
    inCart: false,
    performanceIndex: 544
  },
  {
    brandName: 'Ford',
    modelName: 'Racing Escort MK1',
    year: 1967,
    creditCost: 500000,
    imgURL: './vue-project/public/img/fh5-newfords-escort-20210825.jpg',
    inCart: false,
    performanceIndex: 636
  },
  {
    brandName: 'Ford',
    modelName: 'Super Duty F-450 DRW Platinum',
    year: 2020,
    creditCost: 70000,
    imgURL: './vue-project/public/img/fh5-newfords-f450-20210825.jpg',
    inCart: false,
    performanceIndex: 466
  },
  {
    brandName: 'Porsche',
    modelName: "#65 Rothsport Racing 911 'Desert Flyer'",
    year: 1989,
    creditCost: 500000,
    imgURL: './vue-project/public/img/fh5-carlist-porsche-964desert-20210903-800x450.jpg',
    inCart: false,
    performanceIndex: 694
  },
  {
    brandName: 'Porsche',
    modelName: 'Macan Rally Raid',
    year: 2018,
    creditCost: 250000,
    imgURL: './vue-project/public/img/fh5-carlist-porsche-macanrr-20210903-800x450.jpg',
    inCart: false,
    performanceIndex: 637
  },
  {
    brandName: 'Porsche',
    modelName: 'Taycan Turbo S',
    year: 2020,
    creditCost: 185000,
    imgURL: './vue-project/public/img/fh5-carlist-porsche-taycan-20210903.jpg',
    inCart: false,
    performanceIndex: 807
  }
])

const filteredCarList = computed(() => {
  return carList.value.filter((car) => car.inCart === true)
})

function calcSum(array, property) {
  let sum = 0
  array.forEach((entry) => {
    sum += entry[property]
  })
  return sum
}

const selectedMsg = ref('IN CART')
const defaultMsg = ref('ADD TO CART')
</script>

<template>
  <h1 id="title-banner">FORZA HORIZON 5 CARS</h1>
  <div id="content-bin">
    <div class="card-bin" style="height: 91vh">
      <!-- <div class="car-card" v-for="car in carList" :key="car.performanceIndex">
      <CarImage
        :imageURL="car.imgURL"
        :imageAlt="`Image of a ${car.year} ${car.brandName} ${car.modelName}`"
      />
      <PerformanceIndexIcon
        :carClass="getCarClass(car.performanceIndex).className"
        :performanceIndex="car.performanceIndex"
        :classColor="getCarClass(car.performanceIndex).color"
      />
      <h2>{{ car.brandName }}</h2>
      <h2>{{ car.modelName }}</h2>
      <h2>{{ car.year }}</h2>
      <CartButton
        :defaultText="defaultMsg"
        :selectedText="selectedMsg"
        :selectedStatus="car.inCart"
        :buttonBackgroundColor="getCarClass(car.performanceIndex).color"
        @click="car.inCart = !car.inCart"
      />
    </div> -->
      <CarCard
        v-for="car in carList"
        :key="car.performanceIndex"
        :carCost="car.creditCost"
        :carYear="car.year"
        :carBrandName="car.brandName"
        :carModelName="car.modelName"
        :carImageURL="car.imgURL"
        :carImageAlt="`Image of a ${car.year} ${car.brandName} ${car.modelName}`"
        :carClassName="getCarClass(car.performanceIndex).className"
        :carPerformanceIndex="car.performanceIndex"
        :classColor="getCarClass(car.performanceIndex).color"
        :btnDefaultText="defaultMsg"
        :btnSelectedText="selectedMsg"
        :cartSelectedStatus="car.inCart"
        @response="car.inCart = !car.inCart"
      />
    </div>
    <div id="cart-bin">
      <div class="card-bin" style="height: 75vh">
        <CarCard
          v-for="car in filteredCarList"
          :key="car.performanceIndex"
          :carCost="car.creditCost"
          :carYear="car.year"
          :carBrandName="car.brandName"
          :carModelName="car.modelName"
          :carImageURL="car.imgURL"
          :carImageAlt="`Image of a ${car.year} ${car.brandName} ${car.modelName}`"
          :carClassName="getCarClass(car.performanceIndex).className"
          :carPerformanceIndex="car.performanceIndex"
          :classColor="getCarClass(car.performanceIndex).color"
          :btnDefaultText="defaultMsg"
          :btnSelectedText="selectedMsg"
          :cartSelectedStatus="car.inCart"
          @response="car.inCart = !car.inCart"
        />
      </div>
      <div id="cart-info">
        <p>Items: {{ filteredCarList.length }}</p>
        <p>Total Cost: CR {{ calcSum(filteredCarList, 'creditCost') }}</p>
      </div>
    </div>
  </div>

  <RouterView />
</template>

<style scoped>
#title-banner {
  width: 100vw;
  height: 9vh;
  font-size: 7.5vh;
  background-color: rgb(232, 51, 130);
  color: white;
  display: flex;
  align-content: center;
  justify-content: center;
}

h2 {
  font-size: 3rem;
}

img {
  /* width: 40rem; */
}

.card-bin {
  display: flex;
  flex-wrap: wrap;
  align-content: flex-start;
  justify-content: space-around;
  overflow: auto;
  /* overflow-x: hidden; */

  /* Hide scrollbar for IE, Edge and Firefox */
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
}

/* Hide scrollbar for Chrome, Safari and Opera */
.card-bin::-webkit-scrollbar {
  display: none;
}

#cart-bin {
  background-color: rgba(100, 100, 100, 0.5);
  width: 145rem;
  margin: 2.5rem;
}

#cart-info {
  /*border-color: rgba(255, 255, 255, 0.7);
  border-width: 0.5rem;
  border-style: solid;*/
  height: 10vh;
  width: 50rem;
  color: rgba(255, 255, 255, 0.7);
  height: 0.75rem;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  flex-direction: column;
  font-size: 5rem;
  font-weight: 600;
  padding: 2.5rem;
}

#content-bin {
  display: flex;
  flex-wrap: nowrap;
  flex-direction: row;
  align-content: space-around;
  justify-content: space-around;
}
</style>
