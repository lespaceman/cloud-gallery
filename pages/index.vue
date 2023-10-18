<template>
  <div class="h-[100vh] bg-gradient-to-t from-slate-600 from-20% via-slate-700 via-30% to-slate-900 to-90% z-20">
    <div class="header fixed top-0 ">
      <h1 class="text-5xl font-extrabold text-white py-12 px-4">Global Dev Conf 2023</h1>
    </div>

    <div class="pt-[188px]">
      <div class="bg-white rounded-t-3xl z-10 absolute">
        <People :setSelectPerson="setSelectPerson" />
        <Gallery :open="openModal" :select="select" :galleryItems="galleryItems" />
        <Footer />
      </div>
    </div>

    <Modal :isOpen="isOpen" :closeModal="closeModal" :openModal="openModal">
      <ImageViewer :selectedImage="selectedImage" />
    </Modal>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const isOpen = ref(false)
const selectedImage = ref()
const selectedPerson = ref()
const galleryItems = ref(gallery)


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
const setSelectPerson = (id) => {
  selectedPerson.value = id
  if (id) {
    const newGallery = galleryItems.value.filter((item) => {
      return item.people.includes(Number(id))
    })
    galleryItems.value = newGallery
    return
  }
  galleryItems.value = gallery
}
</script>
