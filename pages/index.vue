<template>
  <div class="h-[100vh] bg-gradient-to-t from-slate-600 from-20% via-slate-700 via-30% to-slate-900 to-90%">
    <div class="header">
      <h1 class="text-5xl font-extrabold text-white py-12 px-4 fixed">Global Dev Conf 2023</h1>
    </div>
    <div class="h-[100vh] bg-white rounded-t-3xl absolute top-[188px]">
      <People />
      <Gallery :open="openModal" :select="select" />
      <Modal :isOpen="isOpen" :closeModal="closeModal" :openModal="openModal">
        <ImageViewer :selectedImage="selectedImage" />
      </Modal>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const isOpen = ref(false)
const selectedImage = ref()

function closeModal() {
  isOpen.value = false
}
function openModal() {
  isOpen.value = true
}
function select(event) {
  const item = gallery.find((item) => item.id == event.target.id)
  selectedImage.value = item.src
  openModal()
}
</script>
