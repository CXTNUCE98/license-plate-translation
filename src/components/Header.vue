<script setup lang="ts">
const Logo = ref()
const BgHome = ref()
const BgAbout = ref()

const route = useRoute()

const props = defineProps({
    isStuck: Boolean,
})
const nav = ref([
    { label: 'Home', to: '/', active: true },
    { label: 'About', to: '/about' },
    { label: 'Service', to: '/service' },
    { label: 'Upcoming Packages', to: '/packages' },
])

const curRoute = computed(() => {
    return route.path as string
})

const bgHeader = {
    '/': BgHome,
    '/about': BgAbout,
}
const isShowMenu = ref(false)
function toggle() {
    console.log('running');
    isShowMenu.value = !isShowMenu.value
}


const isCenter = computed(() => {
    return curRoute.value !== '/'
})

const { x, y } = useWindowScroll()
const isStuck = computed(() => {
    return y.value > 0  ? true : false   
})
</script>

<template>
    <nav :class="{ 'stuck': isStuck }"
        class="border-gray-200 dark:bg-gray-900 relative flex w-full justify-center header-main">
        <div class="relative w-full max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4 z-10">
            <NuxtLink to="/" class="flex items-center space-x-3 rtl:space-x-reverse">
                <img :src="Logo" class="h-16 rounded-full" alt="Logo" />
            </NuxtLink>
            <button @click="toggle" data-collapse-toggle="navbar-default" type="button"
                class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600"
                aria-controls="navbar-default" aria-expanded="false">
                <span class="sr-only">Open main menu</span>
                <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
                    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                        d="M1 1h15M1 7h15M1 13h15" />
                </svg>
            </button>
            <div class="hidden w-full md:block md:w-auto" :class="{ '!block': isShowMenu }" id="navbar-default">
                <ul
                    class="font-medium flex flex-col p-4 md:p-0 mt-4 border bg-gray-50 border-gray-100 rounded-lg md:flex-row md:space-x-8 rtl:space-x-reverse md:mt-0 md:border-0 md:bg-transparent dark:bg-gray-800 md:dark:bg-gray-900 dark:border-gray-700">
                    <template v-for="(item, index) in nav" :key="index">
                        <li class="relative flex justify-center">
                            <NuxtLink
                                class="block py-2 px-3 rounded hover:bg-gray-100 md:hover:bg-transparent md:border-0 md:hover:text-#DF6951 md:p-0  dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent"
                                :class="{ 'active': item.to === curRoute }" :to="item.to">
                                {{ item.label }}
                            </NuxtLink>
                        </li>
                    </template>
                </ul>
            </div>
        </div>

        <div v-if="isCenter" class="absolute flex justify-center items-center w-full h-80% flex-col">
            <div class="text-rose-50 text-lg font-bold font-['Poppins'] uppercase tracking-widest">Read</div>
            <div class="text-white text-38 font-normal yesteryear-regular leading-56">About Us</div>
        </div>
        <div v-else class="absolute "></div>
    </nav>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Yesteryear&display=swap');

.yesteryear-regular {
    font-family: "Yesteryear", cursive;
    font-weight: 400;
    font-style: normal;
}

.active::before {
    content: '';
    position: absolute;
    border-bottom: 4px solid #DF6951;
    width: 40px;
    bottom: -3px;
    left: 50%;
    transform: translateX(-50%);
}

.header-main {
    height: 70px !important;
    -webkit-box-shadow: 1px 1px 10px rgb(0 0 0 / 15%);
}

.stuck {
    animation: stuckMoveDown .6s;
    top: 0;
    position: fixed;
    left: 0;
    right: 0;
    margin: 0 auto;
}

@keyframes stuckMoveDown {
    0% {
        webkit-transform: translateY(-100%);
        transform: translateY(-100%)
    }

    100% {
        webkit-transform: translateY(0);
        transform: translateY(0)
    }
}
</style>