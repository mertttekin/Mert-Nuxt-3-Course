<template>
    <div class="h-screen bg-cyan-100 items-center justify-center flex">
        <div class="text-2xl bg-slate-300 w-1/3 text-center rounded-2xl p-10">
            <h1 class="font-medium p-3">Hello From Counter</h1>
            <div>
                <h6 class="font-medium p-3">{{counter}}</h6>
                <button @click="counter++" class="border w-20 m-4 bg-slate-500 rounded-3xl text-cyan-50 ">+</button>
                <button @click="counter--" class="border w-20 m-4 bg-slate-500 rounded-3xl text-cyan-50 ">-</button>
            </div>
        </div>
    </div>
</template>

<script setup>
    const counter = ref(0);
</script>