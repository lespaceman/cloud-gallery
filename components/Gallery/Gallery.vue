<template>
    <div class="gallery px-4">
        <div class="pb-4 flex items-center justify-between">
            <h1 class=" text-xl font-bold text-slate-900">Gallery</h1>
        </div>
        <div class="flex flex-wrap gap-2">
            <div class="image rounded overflow-hidden" v-for="(image, index) in gallery" :key="index">
                <img class="" :src="image.img" alt="" />
            </div>

        </div>

    </div>
</template>