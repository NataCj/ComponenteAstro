<script setup>
import { ref } from 'vue'

let msg = ref("Soy un tooltip");
let checked = ref(false);

let data = ["hola", "mundo", "cruel"];

</script>

<template>
    <div class="bg-red-600 p-4 mx-auto max-w-60">
        <input class="border  border-blue-600 " :class="{ 'border-green-500': checked }" v-model="msg">
        <div :title="msg">
            {{ msg }}
        </div>

        <label for="check">seleccionado {{ checked }}</label>
        <input type="checkbox" v-model="checked">

        <ul>
            <li v-for="(text, index) in data" :key="index">
                {{ text }}
            </li>
        </ul>
    </div>
</template>