<template>
    <div class="p-4">
        <div class="pb-4 flex items-center justify-between">
            <h1 class=" text-xl font-bold text-slate-900">People</h1>
            <button class="px-2 py-[2px] bg-slate-300 rounded-lg h-fit">View all</button>
        </div>
        <div class="people">
            <div class="flex gap-3 justify-evenly">
                <div class="person rounded-[50%] overflow-hidden w-[80px] h-[80px]" v-for="(person, index) in people"
                    :key="index">
                    <img class="w-[80px] h-[80px]" :src="person.img" alt="" />
                </div>
            </div>
        </div>
    </div>
</template>
