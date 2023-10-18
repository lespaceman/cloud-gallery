<template>
    <div class="p-4">
        <div class="pb-4">
            <h1 class="text-xl font-bold text-slate-800">People</h1>
            <span class="text-slate-600 text-sm">Find people in the gallery by their face</span>
        </div>
        <div class="people">
            <div class="flex gap-3 justify-start">
                <div class="person rounded-[50%] overflow-hidden w-[80px] h-[80px]"
                    :class="[{ 'ring-offset-2 ring-2 ring-blue-500': person.id == selectedPerson }, { 'opacity-25': selectedPerson && person.id != selectedPerson }]"
                    v-for="(person, index) in    people   " :key="index">
                    <img class="w-[80px] h-[80px] object-cover" :src="person.img" :id="person.id" @click="onSelect" />
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const selectedPerson = ref()
const { setSelectPerson } = defineProps(['setSelectPerson'])

watch(selectedPerson, (id) => {
    setSelectPerson(id)
})
const onSelect = (event) => {
    if (selectedPerson.value === event.target.id) {
        selectedPerson.value = undefined
    } else {
        selectedPerson.value = event.target.id
    }
}
</script>
