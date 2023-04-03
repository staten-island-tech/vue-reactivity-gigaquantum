<script setup>
const props = defineProps({
  imageURL: String,
  imageAlt: String
})
</script>

<template>
  <div class="img-bin"><img :src="imageURL" :alt="imageAlt" /></div>
</template>

<style scoped>
.img-bin {
  /* border: orange solid 0.25rem; 8 */
  /* overflow: hidden;
  padding: 0rem;
  width: 74%;
  height: 80%; */
}

img {
  /* clip-path: margin-box;
  clip-path: polygon(0 0, 74% 0%, 74% 100%, 0 100%);
  shape-outside: content-box;
  box-sizing: content-box; */

  /* width: 66.5rem;
  height: 29.5rem;
  object-fit: none;
  object-position: left center; */
  /* bottom: 0;
  left: 0;
  right: 0;
  top: 0;
  transform: translateX(26%); */
  width: 37.5rem;
}
</style>
