<script setup>
    import {
        reactive,
        ref,
    } from 'vue';

    const lightOnImage = ref('//img.icons8.com/?size=512&id=12244&format=png');
    const lightOffImage = ref('https://img.icons8.com/?size=512&id=75&format=png');

    const lightOneOptions = reactive([
        {
            image: '//img.icons8.com/?size=512&id=12244&format=png',
            switch: true,
            text: 'On',
            backgrounnd: 'bg-blue-500',
            btnHover: 'hover:bg-blue-700'
        }
    ])

    function lightOneClicked(lightOneSwitch){
        if(lightOneSwitch){
            lightOneOptions[0].image = lightOffImage.value
            lightOneOptions[0].switch = false
            lightOneOptions[0].text = 'Off'
            lightOneOptions[0].backgrounnd = 'bg-gray-500'
            lightOneOptions[0].btnHover = 'hover:bg-gray-700'
        }else{
            lightOneOptions[0].image = lightOnImage.value
            lightOneOptions[0].switch = true
            lightOneOptions[0].text = 'On'
            lightOneOptions[0].backgrounnd = 'bg-blue-500'
            lightOneOptions[0].btnHover = 'hover:bg-blue-700'
        }
    }


    const lightTwoOptions = reactive([
        {
            image: '//img.icons8.com/?size=512&id=12244&format=png',
            switch: true,
            text: 'On',
            backgrounnd: 'bg-blue-500',
            btnHover: 'hover:bg-blue-700'
        }
    ])

    function lightTwoClicked(lightTwoSwitch){
        if(lightTwoSwitch){
            lightTwoOptions[0].image = lightOffImage.value
            lightTwoOptions[0].switch = false
            lightTwoOptions[0].text = 'Off'
            lightTwoOptions[0].backgrounnd = 'bg-gray-500'
            lightTwoOptions[0].btnHover = 'hover:bg-gray-700'
        }else{
            lightTwoOptions[0].image = lightOnImage.value
            lightTwoOptions[0].switch = true
            lightTwoOptions[0].text = 'On'
            lightTwoOptions[0].backgrounnd = 'bg-blue-500'
            lightTwoOptions[0].btnHover = 'hover:bg-blue-700'
        }
    }


    const lightThreeOptions = reactive([
        {
            image: 'https://img.icons8.com/?size=512&id=75&format=png',
            switch: false,
            text: 'Off',
            backgrounnd: 'bg-gray-500',
            btnHover: 'hover:bg-gray-700'
        }
    ])

    function lightThreeClicked(lightThreeSwitch){
        if(lightThreeSwitch){
            lightThreeOptions[0].image = lightOffImage.value
            lightThreeOptions[0].switch = false
            lightThreeOptions[0].text = 'Off'
            lightThreeOptions[0].backgrounnd = 'bg-gray-500'
            lightThreeOptions[0].btnHover = 'hover:bg-gray-700'
        }else{
            lightThreeOptions[0].image = lightOnImage.value
            lightThreeOptions[0].switch = true
            lightThreeOptions[0].text = 'On'
            lightThreeOptions[0].backgrounnd = 'bg-blue-500'
            lightThreeOptions[0].btnHover = 'hover:bg-blue-700'
        }
    }

</script>

<template>
    <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Assignment</h1>
        <p class="p-5">Make These Buttons Work</p>
        <div class="flex justify-between space-x-6">
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <button class="text-white font-bold py-2 px-4 rounded" :class="[lightOneOptions[0].backgrounnd, lightOneOptions[0].btnHover]" @click="lightOneClicked(lightOneOptions[0].switch)">
                        Light 1 {{ lightOneOptions[0].text }}
                    </button>
                <button class="text-white font-bold py-2 px-4 rounded" :class="[lightTwoOptions[0].backgrounnd, lightTwoOptions[0].btnHover]" @click="lightTwoClicked(lightTwoOptions[0].switch)">
                        Light 2 {{ lightTwoOptions[0].text }}
                    </button>
                 <button class="text-white font-bold py-2 px-4 rounded" :class="[lightThreeOptions[0].backgrounnd, lightThreeOptions[0].btnHover]" @click="lightThreeClicked(lightThreeOptions[0].switch)">
                        Light 3 {{ lightThreeOptions[0].text }}
                 </button> 
            </div>
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <img class="w-20" :src="lightOneOptions[0].image" alt="">
                 <img class="w-20" :src="lightTwoOptions[0].image" alt="">
                 <img class="w-20" :src="lightThreeOptions[0].image" alt="">
            </div>
        </div>
    </section>
</template>

<style scoped>

</style>
