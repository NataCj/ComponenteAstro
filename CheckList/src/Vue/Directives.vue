<script setup>
import {ref} from 'vue'

let msg = ref("Soy un tooltip");
let checked = ref(false);

let data = ["hola", "mundo", "bonito"];
</script>

<template>
    <input class="border border-red-500 " :class="{'border-green-500': checked}" v-model = "msg" >
    <div :title="msg">
        {{ msg }}
    </div>

    <label for="check">seleccionado {{ checked }}</label>
    <input type="checkbox" v-model="checked">

    <ul>
        <li v-for="(text, index) in data" :key = "index">
        {{ text }}
        </li>
    </ul>
</template>