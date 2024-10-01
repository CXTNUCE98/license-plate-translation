<script setup lang="ts">
import emblaCarouselVue from 'embla-carousel-vue'
import Autoplay from 'embla-carousel-autoplay'

import Switzerland from "@/public/switzerland.png"
import Amazon from "@/public/amazon.png"
import Giza from "@/public/giza.png"

const destinations = [
    {
        img: Switzerland,
        name: 'Switzerland',
        avatar: 'https://i.pinimg.com/564x/2b/02/ed/2b02ed6a09c68b3792e9c785dfed5002.jpg',
        price: 1000,
        discount: 1200,
        location: 'Europe',
        day: 8,
        people: 25,
        des: 'Nam exercitationem commodi et ducimus quia in dolore animi sit mollitia amet id quod eligendi. Et labore harum non nobis ipsum eum molestias mollitia et corporis praesentium a laudantium internos.',
    },
    {
        img: Amazon,
        name: 'Amazon',
        avatar: 'https://i.pinimg.com/564x/16/e2/be/16e2be5829763ab4ea663a591a165867.jpg',
        price: 1223,
        discount: 1400,
        location: 'Brazil',
        day: 8,
        people: 30,
        des: 'Nam exercitationem commodi et ducimus quia in dolore animi sit mollitia amet id quod eligendi. Et labore harum non nobis ipsum eum molestias mollitia et corporis praesentium a laudantium internos.',
    },
    {
        img: Giza,
        name: 'Giza',
        avatar: 'https://i.pinimg.com/564x/be/6d/67/be6d6737a0d9f460f25daa88c71438e7.jpg',
        price: 1200,
        discount: 1500,
        location: 'Egypt',
        day: 8,
        people: 155,
        des: 'Nam exercitationem commodi et ducimus quia in dolore animi sit mollitia amet id quod eligendi. Et labore harum non nobis ipsum eum molestias mollitia et corporis praesentium a laudantium internos.',
    },
    {
        img: 'https://ik.imagekit.io/tvlk/blog/2023/07/thap-eiffel-1-1024x678.jpg?tr=dpr-2,w-675',
        name: 'Eiffel',
        avatar: 'https://i.pinimg.com/originals/2f/80/3d/2f803d5a75641a70db78414bcf62b0cd.png',
        price: 1000,
        discount: 1200,
        location: 'France',
        day: 8,
        people: 25,
        des: 'Nam exercitationem commodi et ducimus quia in dolore animi sit mollitia amet id quod eligendi. Et labore harum non nobis ipsum eum molestias mollitia et corporis praesentium a laudantium internos.',
    },
    {
        img: 'https://ik.imagekit.io/tvlk/blog/2023/04/quang-truong-thoi-1-1024x576.jpg?tr=dpr-2,w-675',
        name: 'New York times square',
        avatar: 'https://i.pinimg.com/564x/41/8a/1e/418a1e5d977ed08a8a3c720b35057e96.jpg',
        price: 1223,
        discount: 1400,
        location: 'American',
        day: 8,
        people: 30,
        des: 'Nam exercitationem commodi et ducimus quia in dolore animi sit mollitia amet id quod eligendi. Et labore harum non nobis ipsum eum molestias mollitia et corporis praesentium a laudantium internos.',
    },
    {
        img: 'https://ik.imagekit.io/tvlk/blog/2022/10/kinh-nghiem-du-lich-vinh-ha-long-3.jpg?tr=dpr-2,w-675',
        name: 'Ha Long bay',
        avatar: 'https://i.pinimg.com/564x/6a/51/b6/6a51b6a5ae3a430d81986e1d0867ee20.jpg',
        price: 1200,
        discount: 1500,
        location: 'Vietnam',
        day: 8,
        people: 1550,
        des: 'Nam exercitationem commodi et ducimus quia in dolore animi sit mollitia amet id quod eligendi. Et labore harum non nobis ipsum eum molestias mollitia et corporis praesentium a laudantium internos.',
    },
    {
        img: 'https://ik.imagekit.io/tvlk/blog/2022/10/kinh-nghiem-du-lich-vinh-ha-long-3.jpg?tr=dpr-2,w-675',
        name: 'Phong Nha Ke Bang Cave',
        avatar: 'https://i.pinimg.com/564x/6a/51/b6/6a51b6a5ae3a430d81986e1d0867ee20.jpg',
        price: 1200,
        discount: 1500,
        location: 'Vietnam',
        day: 8,
        people: 1155,
        des: 'Nam exercitationem commodi et ducimus quia in dolore animi sit mollitia amet id quod eligendi. Et labore harum non nobis ipsum eum molestias mollitia et corporis praesentium a laudantium internos.',
    },
]

const [emblaRef] = emblaCarouselVue({ loop: true, align: 'start' }, [Autoplay()])
</script>
<template>
    <div class="carousel-container">
        <div class="embla" ref="emblaRef">
            <div class="embla__container">
                <div v-for="(item, index) in destinations" :key="index"
                    class="basis-1/1 py-4 2xl:basis-1/5 lg:basis-1/3 md:basis-1/2 xl:basis-1/4">
                    <div
                        class="card border-border rounded-2xl leading-normal! hover:shadow-lg hover:-translate-y-3 cursor-pointer">
                        <div class="image-container">
                            <img :src="item?.img" class="block w-392px h-312px pixelated rounded-12px object-cover">
                            <img :src="item?.avatar" alt="avatar" class="absolute bottom--40px left-20px rounded-full w-80px h-80px object-cover border-4 border-white">
                        </div>
                        <div class="flex pt-10 gap-10">
                            <div
                                class="flex gap-1 items-center text-center text-zinc-500 text-[16.81px] font-normal font-['Poppins'] capitalize">
                                <i class='bx bx-calendar-alt'></i>
                                <span>{{ item.day }} Days</span>
                            </div>
                            <div
                                class="flex gap-1 items-center text-center text-zinc-500 text-[16.81px] font-normal font-['Poppins'] capitalize">
                                <i class='bx bx-user'></i>
                                <span>{{ item.people }} People Going</span>
                            </div>
                        </div>

                        <div class="flex justify-between items-center">
                            <div class="text-center text-zinc-800 text-[29.03px] font-bold capitalize line-clamp-1 text-left w-180px"><SharedEllipsis :content="item.name" /></div>
                            <div class="text-yellow-400">
                                <i class='bx bxs-star'></i>
                                <i class='bx bxs-star'></i>
                                <i class='bx bxs-star'></i>
                                <i class='bx bxs-star'></i>
                                <i class='bx bxs-star'></i>
                            </div>
                        </div>

                        <div class="text-zinc-500 flex items-center gap-1">
                            <i class='bx bx-current-location text-28px'></i>
                            <div class="text-center  text-[16.81px] capitalize">{{ item.location }}</div>
                        </div>

                        <div class="flex items-center gap-6 py-4">
                            <div class="text-center text-red-400 text-[29.03px] font-medium capitalize">{{ item.price }}
                                $
                            </div>
                            <div class="text-center text-zinc-500 text-[22px] font-medium line-through capitalize">
                                {{ item.discount }} $</div>
                        </div>
                        <div
                            class="text-start text-black text-xs font-normal font-['Poppins'] leading-normal tracking-wide">
                            {{ item.des }}</div>

                        <div class="flex justify-start pt-4">
                            <el-button size="large" color="#DF6951">
                                <span class="text-white">
                                    Explore Now
                                </span>
                            </el-button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<style scoped>
.image-container {
    position: relative;
    display: inline-block;
}

.card {
    height: 700px;
    min-width: 320px;
    border: 1px solid var(--el-border-color);
    box-sizing: border-box;
    text-align: center;
    position: relative;
    transition: all .3s ease-in-out;
    bottom: 0;
    margin: auto;
}

.carousel-container {
    width: 1100px;
    overflow: hidden;
    margin: 0 auto;
}

.embla {
    overflow: hidden;
}

.embla__container {
    display: flex;
    gap: 60px;
    padding-left: 60px; 
    padding-right: 30px; 
}

.embla__slide {
    flex: 0 0 100%;
    min-width: 0;
}

.pixelated {
    image-rendering: pixelated;
}
</style>