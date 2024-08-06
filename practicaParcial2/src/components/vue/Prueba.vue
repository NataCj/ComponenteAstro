<script setup>
import {ref} from 'vue';

let number = ref(0);
let time = ref(0);
let interval

function add() {
    if (number.value == 0){
        interval = setInterval(() => {
            time.value ++
        },1000)
    }
    number.value++;
    
    if(number.value == 100){
        clearInterval(interval)
    }
}
</script>
<template>
    <div v-show="number>0" class="float-right mr-8 bg-red-100 rounded inline-block py-1 px-2">
        Tiempo: {{ time }} 🌹
    </div>
    <div @click="add" class="hover:cursor-pointer select-none bg-red-100 py-1 px-2 rounded w-12 text-center mt-10 mx-auto text-red-950">
        {{ number }}
    </div>
    <div v-if="number == 0" class="text-red-600 w-52 mt-8 mx-auto text-center">
        ¿Clickear? !o miedo! 🐱‍👓
    </div>
    <div v-else class="text-green-600 w-52 mt-8 mx-auto text-center">
        GO! GO! GO! 🐱‍💻
    </div>
</template>