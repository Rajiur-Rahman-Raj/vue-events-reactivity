<script setup>

    import { reactive, ref } from 'vue';

    const location = ref('Bogura')
    
    const fullLocation = reactive({
        city: 'Bogura',
        lat: '1234',
        long: '5678'
    })

    function changeLocation(city, lat, long){
      fullLocation.city = city
      fullLocation.lat = lat
      fullLocation.long = long
    }

    const locationBoxBackground = ref("bg-blue-500")

    function changeBackgroundColor(bgColor){
      locationBoxBackground.value = bgColor
    }

</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
    <h1 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h1>
    <div class="container mx-auto flex space-x-5 justify-center m-5">
      <button class="hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" :class="locationBoxBackground" @click="changeLocation('Dhaka', '#0987', '#1234')">
               Dhaka
        </button> 
      <button class="hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" :class="locationBoxBackground" @click="changeLocation('Rajshahi')">
              Rajshahi
        </button>
      <button class="hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" :class="locationBoxBackground" @click="changeLocation('Rangpur')">
              Rangpur
        </button>
    </div>
    <h1 class="text-2xl m-10">Current Location is</h1>
    <hr>
    <h2> City       = {{ fullLocation.city }}</h2>
    <h3> Latitute   = {{ fullLocation.lat }}</h3>
    <h4> Longtitute = {{ fullLocation.long }}</h4>

    <div class="mt-10 flex justify-center space-x-5">
      <div class="w-10 h-10 bg-orange-700" @click="changeBackgroundColor('bg-orange-700')"></div>
      <div class="w-10 h-10 bg-indigo-700" @click="changeBackgroundColor('bg-indigo-700')"></div>
      <div class="w-10 h-10 bg-purple-700" @click="changeBackgroundColor('bg-purple-700')"></div>
    </div>

  </section>
</template>

<style scoped>

</style>
