<script setup lang="ts">
import emblaCarouselVue from 'embla-carousel-vue'
import Autoplay from 'embla-carousel-autoplay'

const [emblaRef] = emblaCarouselVue({ loop: true, align: 'start' }, [Autoplay()])

import Watch from "@/public/watch-london.png"
import Italia from "@/public/italia.png"
import Colosseum from "@/public/colosseum.png"
import Berlin from "@/public/berlin.png"


const destinations = [
    {
        img: Watch,
        name: 'London Watch',
        price: 700,
    },
    {
        img: Italia,
        name: 'The Ijssel River',
        price: 800,
    },
    {
        img: Colosseum,
        name: 'The Colosseum',
        price: 500,
    },
    {
        img: Berlin,
        name: 'Berlin Cathedral',
        price: 400,
    },
    {
        img: Colosseum,
        name: 'The Colosseum',
        price: 500,
    },
    {
        img: Berlin,
        name: 'Berlin Cathedral',
        price: 400,
    },
    {
        img: Colosseum,
        name: 'The Colosseum',
        price: 500,
    },
    {
        img: Berlin,
        name: 'Berlin Cathedral',
        price: 400,
    },
]

const isShowTourDetail = ref(false)
const detail = ref()

function openDetail(info: any) {    
    detail.value = info
    console.log('detail: ', detail);
    isShowTourDetail.value = true
    
}
</script>

<template>
    <div class="carousel-container" >
        <div class="relative embla mx-10" ref="emblaRef" >
            <div class="embla__container">
                <div v-for="(item, index) in destinations" :key="index" class="basis-1/1 px-2 py-4 2xl:basis-1/5 lg:basis-1/3 md:basis-1/2 xl:basis-1/4">
                    <SharedDestinationCard :product="item" @openDetail="openDetail(item)"/>
                </div>
            </div>
        </div>
    </div>

    <TourDetailDialog :visible="isShowTourDetail" :info="detail" @close="isShowTourDetail = false"/>
</template>

<style scoped>
.carousel-container {
    width: 1100px;
    overflow: hidden;
    position: absolute;
    margin: 0 auto;
}

.embla {
    overflow: hidden;
}

.embla__container {
    display: flex;
}

.embla__slide {
    flex: 0 0 auto;
    width: 100%;
    min-width: 0;
}
</style>