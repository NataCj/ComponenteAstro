<script setup>

import { ref, computed } from "vue";

const carSlots = ref([
   {active: true, value: 1000},
   {active: true, value: 1100},
   {active: true, value: 1200},
   {active: true, value: 1300},
   {active: true, value: 1400},
   {active: true, value: 1500},


]);

const bikeSlots = ref ([
   {active: true, value: 200},
   {active: true, value: 200},
   {active: true, value: 200},




]);

const total = ref(0);

const toggleCarSlot = (index) => {
    const car = carSlots.value[index];
    car.active = !car.active;
    if (car.active){
        total.value += car.value;


    }
};

const toggleBikeSlot = (index) => {
  const bike = bikeSlots.value[index];
  bike.active = !bike.active;
  if (bike.active) {
    total.value += bike.value;
  }
};

const restartTotal = computed(function(){
    total.value -= total.value
})

</script>


<template>


<div class="mx-auto p-4 ">
 <h1 class="font-bold mb-4 text-2xl">Parqueadero</h1>

    <div class="mb-8">
        <h2 class="text-xl font-semibold mb-2">Carriles de Motos</h2>
        <div class="grid-cols-3 grid gap-4">
            <div v-for="(car,index) in carSlots" :key="index">
                <div @click="toggleCarSlot(index)" :class="car.active ? 'bg-green-500 hover:bg-green-600' : 'bg-red-500 hover:bg-red-600'" class=" w-20 h-20 flex justify-center items-center text-white rounded-md cursor-pointer">
                 {{ car.active ? 'Libre' : 'Ocupado' }}
                </div>
            </div>
        </div>
    </div>

   <div>
  <h2 class="text-2xl font-semibold mb-2">Carriles de Motos</h2>
          <div class="grid grid-cols-3 gap-4">
               <div v-for="(bike,index) in bikeSlots" :key= "index">
                <div @click="toggleBikeSlot(index)" :class="bike.active ? 'bg-green-500 hover:bg-green-600 ':'bg-red-500 hover:bg-red-600'" class="w-20 h-20 flex justify-center items-center text-white rounded-md cursor-pointer">
                 {{ bike.active ? 'Libre' : 'Ocupado' }}
    
                </div>
        </div>
    </div>
 </div>
</div>

<div class="mt-12 " ></div>
 <div>
    <h2 class="text-xl font-semibold ml-10">TOTAL A PAGAR</h2>
    <p class="text-2xl font-bold text-cyan-500 ml-10 ">Total: {{ total }}</p>
 </div>

 <div>
    <button @click="restartTotal" class="p-4 bg-yellow-500 rounded mt-5 ml-10  ">Reiniciar</button>
 </div>
</template>