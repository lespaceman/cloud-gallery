<template>
    <img :src="selectedImage" :alt="selectedImage" />
</template>

<script setup>
const { selectedImage } = defineProps(['selectedImage', 'select'])
</script>