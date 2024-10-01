<script setup lang="ts">

import Guided from "@/public/guided.png"
import Flight from "@/public/flight.png"
import Religious from "@/public/religious.png"
import Medical from "@/public/medical.png"

const categories = [
    {
        img: Guided,
        title: 'Guided Tours',
        des: 'sunt qui repellat saepe quo velit aperiam id aliquam placeat.',
    },
    {
        img: Flight,
        title: 'Best Flights Options',
        des: 'sunt qui repellat saepe quo velit aperiam id aliquam placeat.',
    },
    {
        img: Religious,
        title: 'Religious Tours',
        des: 'sunt qui repellat saepe quo velit aperiam id aliquam placeat.',
    },
    {
        img: Medical,
        title: 'Medical insurance',
        des: 'sunt qui repellat saepe quo velit aperiam id aliquam placeat.',
    },

] 
</script>

<template>
    <div class="flex justify-between pt-8 w-full flex-wrap">
        <div v-for="item in categories" :key="item.img" class="flex flex-col items-center justify-center"> 
            <img :src="item.img" class="h-85px">
            <div class="font-bold text-20px text-#1E1D4C py-4">{{ item.title }}</div>
            <p class="max-w-200px text-#5E6282 font-sans text-center">{{ item.des }}</p>
        </div>
    </div>
</template>
<style scoped></style>