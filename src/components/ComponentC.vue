<template>
    <div class="container">
    <div>Component B</div>
    <h3>Counter - {{ count }}</h3>
    <h3>Double Counter - {{ doubleCount }}</h3>
    <button @click="counterStore.increment">+</button>
    <button @click="counterStore.decrement">-</button> 
    </div>
</template> 
<script setup>
 import { useCounterStore } from '../stores/CounterStore'
 import { storeToRefs } from 'pinia' 
 const counterStore = useCounterStore()
 const { count, doubleCount } = storeToRefs(counterStore)
</script>