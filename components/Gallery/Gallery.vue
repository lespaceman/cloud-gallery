<template>
    <div class="gallery px-4">
        <div class="pb-4">
            <h1 class="text-xl font-bold text-slate-800">Gallery</h1>
            <span class="text-slate-600 text-sm">Here are all the pictures from the event</span>
        </div>
        <div class="grid grid-cols-2 gap-2 pb-8">
            <div class="image rounded object-cover" @click="select" v-for="(image, index) in galleryItems" :key="index">
                <img class="object-cover w-full h-full rounded" :src="image.src" alt="" :id="image.id" />
            </div>
        </div>
    </div>
</template>

<script setup>
const { galleryItems } = defineProps(['galleryItems','select'])
</script>