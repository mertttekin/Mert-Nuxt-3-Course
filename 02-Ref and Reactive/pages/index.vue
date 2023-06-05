<template>
    <div class="h-screen bg-cyan-100 items-center justify-center flex">
        <div class="text-2xl bg-slate-300 w-1/3 text-center rounded-2xl p-10">
            <h1 class="font-medium p-3">{{ counterData.title }}</h1>
            <div>
                <h6 class="font-medium p-3">{{counterData.count}}</h6>
                <button @click="counterData.count++" class="border w-20 m-4 bg-slate-500 rounded-3xl text-cyan-50 ">+</button>
                <button @click="counterData.count--" class="border w-20 m-4 bg-slate-500 rounded-3xl text-cyan-50 ">-</button>
            </div>
            <h1 class="font-medium p-3">Edit this title</h1>
            <input v-model="counterData.title" type="text" class="font-medium p-3 border-none"/>
            
        </div>
    </div>
</template>

<script setup>
    // const counter = ref(0) ,apptitle = ref("Hello From Counter")

    const counterData = reactive({
        count:0,
        title:"Hello From Counter"
    })
</script>