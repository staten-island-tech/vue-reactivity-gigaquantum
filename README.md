# Reactive Vue.js Car Shopping Website
This was a project I used to help me learn Vue 3 that was inspired by Forza Horizon 5. 

## Features
The design includes a list of cars on the left side, and a reactive cart that automatically updates its item count and total price when items are added or removed from the cart. The design also features an animated background that fits the aesthetic of the site, a custom font from Google Fonts, and a static header that sits above the car item cards. 

## Technology
To accomplish this, I used several key features of the Vue.js framework. I opted to use the Vue 3 Composition API. I used Components to make various parts of the car item cards and the car item cards themselves, and passed props into the car item cards using v-for. I used v-bind along with custom functions to dynamically change the background color of the performance rating icon based on the car’s performance rating value. I used v-if to change the cart button’s text and appearance when a car was added or removed from the cart. I used emits to change whether a car’s inCart property was true or false, made a computed list of all of the cars whose inCart property was true, and used v-for to populate the cart section with cars that were in the cart.

Lastly, I used Vite.js to set up my development environment for this project, and used Netlify to host it online.
