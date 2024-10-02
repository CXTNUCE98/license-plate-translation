<script setup lang="ts">
const props = defineProps<{
  value: string | number
}>()
</script>

<template>
    <div class="cursor-pointer px-15px py-9px bg-white flex justify-center items-center text-#AD0909 w-80px h-40px rounded-lg font-bold hover:bg-black hover:text-white">
        {{ value }}
    </div>
</template>
<style scoped>

</style>