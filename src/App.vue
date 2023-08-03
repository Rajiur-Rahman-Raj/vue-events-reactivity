<script setup>
    import {
        ref
    } from 'vue';

    const output = ref('Hellow vue 3')
    const keyPress = ref(0)

    function spaceCount(){
        spaceCount = keyPress.value++
        output.value = `You pressed space ${spaceCount} times`
    }

    function pressWhat(event){
        // output.value = `You pressed ${event.key}`
        output.value = `You pressed ${event.target.value}`
        console.log(event)
    }

    function ctrlRightClicked(){
        output.value = `you clicked ctrl+right`
    }

    function divClicked(){
        output.value = `div clicked`
        alert('div clicked')
    }

    function buttonClick(){
        output.value = `button clicked`
        alert('button clicked')
    }
</script>

<template>
    <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Events &amp; Reactivity in Vue.js</h1>
        <h2 class="mt-10">{{ output }}</h2>
        <form action="https://google.com/search">
            <div class="container mx-auto flex space-x-5 justify-center m-5">
                <input name="q" type="text" class="border border-gray-500 bg-white p-5" placeholder="Press Space" @keypress.space="spaceCount()">
            </div>

            <div class="container mx-auto flex space-x-5 justify-center m-5">
                <input name="text" type="text" class="border border-gray-500 bg-white p-5" placeholder="Type Something" @keyup="pressWhat($event)">
            </div>

            <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click.prevent>
                 Button 
            </button>

            <button class="bg-blue-500 ml-5 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click.ctrl="ctrlRightClicked()">
                 Ctrol + Right Click 
            </button>
        </form>
        <div class="bg-gray-200 w-[500px] h-80 mt-5 flex items-center justify-center" @click="divClicked()">
            <button class="bg-orange-500 hover:bg-orange-700 text-white font-bold py-2 px-4 rounded" @click.stop="buttonClick()"> 
                Button 
            </button>
        </div>
    </section>
</template>

<style scoped>

</style>
