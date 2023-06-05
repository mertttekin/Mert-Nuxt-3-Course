<template>
    <div class="h-screen bg-cyan-100 items-center justify-center flex">
        <div class="text-2xl bg-slate-300 w-1/3 text-center rounded-2xl p-10">
            <h1 class="font-medium p-3">{{ counterData.title }}</h1>
            <div>
                <h6 class="font-medium p-3">{{ counterData.count }}</h6>
                <div class="flex items-center justify-center">
                    <button @click="DecreseCounter"
                        class="border w-20 m-4 bg-slate-500 rounded-3xl text-cyan-50 ">-</button>
                    <button @click="IncreseCounter"
                        class="border w-20 m-4 bg-slate-500 rounded-3xl text-cyan-50 ">+</button>
                </div>
                <div class="flex items-center justify-center">
                    <button @click="DecreseCounterByInput(counterData.inputValue)"
                        class="border w-20 m-4 bg-slate-500 rounded-3xl text-cyan-50 ">-</button>
                    <input type="number" v-model="counterData.inputValue" class="w-30 h-10" />
                    <button @click="IncreseCounterByInput(counterData.inputValue)"
                        class="border w-20 m-4 bg-slate-500 rounded-3xl text-cyan-50 ">+</button>
                </div>
                <p>This counter is {{ oddOrEven }}</p>
                <button @click="ResetCounter(counterData.inputValue)"
                    class="border w-20 m-4 bg-slate-500 rounded-3xl text-cyan-50 ">Reset</button>
            </div>
            <h1 class="font-medium p-3">Edit this title</h1>
            <input v-model="counterData.title" type="text" class="font-medium p-3 border-none" />
        </div>
    </div>
</template>

<script setup>
// const counter = ref(0) ,apptitle = ref("Hello From Counter")

const counterData = reactive({
    count: 0,
    title: "Hello From Counter",
    inputValue: 0
})

// const oddOrEven = computed(()=>{
//     if (counterData.count % 2 === 0 ) 
//     return "even"
//     return "odd";
// })



watch(()=>counterData.count,(newCount,oldCount )=>{
    console.log(newCount)
    counterData.title = newCount === 7 ? "Oww noooo !!" : "Hello From Counter"
})

const oddOrEven = computed(()=>{
    return counterData.count % 2 === 0 ? "even" : "odd";
})

const ResetCounter = () => {
    counterData.inputValue = 0
}

const IncreseCounter = () => {
    counterData.count = counterData.count + 1
}
const DecreseCounter = () => {
    counterData.count = counterData.count - 1
}
const IncreseCounterByInput = value => {
    counterData.count = counterData.count + value
}
const DecreseCounterByInput = value => {
    counterData.count = counterData.count - value
}
</script>