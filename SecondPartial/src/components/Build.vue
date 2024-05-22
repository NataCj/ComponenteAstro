<script setup>
import { ref, computed } from "vue";
const checked = ref(false);
const count = ref(0);
const items = {"1":"Tema 1","2":"Tema 2","3":"Tema 3","4":"Tema 4"};
const checked1 ={"1":ref(false),"2":ref(false),"3":ref(false),"4":ref(false)}

function message1(item){
    let dos;
    if(checked1[item]){
        dos=false;
        list[item]="+"
    }else{
        dos=true;
        list[item]="-"
    }
    return dos;
}

function estado(item){
    if(checked.value){

    }else{

    }
}
function validar(item){
    if(item==items.value){
        checked = message1(item);
    }
}

</script>
<template>
    <div class="w-1/2 h-1/2 text-blue-900 flex flex-col" v-for="(item, index) in items">
        
        <button class="bg-blue-300 flex rounded-lg justify-evenly m-3 p-5 w-full text-left" @click="validar(item), estado(item)">    
            {{ items[index] }} 
            <div v-if="estado(item)" class="">-</div>
            <div v-else>+</div>
            
        </button>
        <div v-show="counter[item] > 0"  class="bg-blue-200 h-44 rounded-lg justify-evenly m-3 p-5 w-full text-left">
            {{ "texto del tema " + items[index] }}
        </div>

    </div>
    
</template>