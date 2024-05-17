<script setup>

import { ref } from 'vue';

const data = ['Tema 1', 'Tema 2', 'Tema 3', 'Tema 4']

const selectedIndex = ref(0)

function showInfo(i){
    selectedIndex.value = i
}

</script>

<template>
    <div class="bg-blue-500 p-1 max-w-60 mx-auto mt-12  ">
        <div
            v-for="(theme, i) in data"
            :key="i"
        > 
            <h1 
                @click="showInfo(i)"
                class="select-none bg-blue-400 text-white px-1 flex justify-between hover:cursor-pointer"
            >
                {{ theme }}
                <span>{{ selectedIndex == i ? '-' : '+' }}</span>
            </h1>
            <div
                v-show="selectedIndex == i" 
                class="bg-blue-50/50 p-1 mt-1">
                Texto del tema
            </div>
        </div> 
    </div>
</template>