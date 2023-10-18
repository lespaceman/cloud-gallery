<template>
    <div class="p-4">
        <div class="pb-4">
            <h1 class="text-xl font-bold text-slate-800">People</h1>
            <span class="text-slate-600 text-sm">Find people in the gallery by their faces</span>
        </div>
        <div class="people">
            <div class="flex gap-3 justify-start">
                <div class="person rounded-[50%] overflow-hidden w-[80px] h-[80px]" v-for="(person, index) in people"
                    :key="index">
                    <img class="w-[80px] h-[80px] object-cover" :src="person.img" alt="" />
                </div>
            </div>
        </div>
    </div>
</template>
