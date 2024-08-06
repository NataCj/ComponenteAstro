<script setup>
import { ref } from 'vue'
const tasks = ref([]);
const inputTask = ref('');

function addTask(){
    tasks.value.push(inputTask.value)
    console.log(tasks)
}
</script>

<template>

    <div class="py-8 px-10 max-w-96 bg-slate-300 rounded shadow mx-auto mt-10">
        <h1 class="text-center text-lg">Lista de tareas</h1>
        <div class="mt-4 mb-2">
            <input type="text" class="w-4/5" v-model="inputTask">
            <button @click="addTask" class="w-1/5 bg-green-600 text-white font-bold">+</button>
        </div>

        <div class="bg-white/60 px-2" v-for="(task, index) in tasks" :key="index">
            {{ task }}
        </div>
    </div>
</template>