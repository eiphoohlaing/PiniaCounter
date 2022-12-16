<template>
  <div class="container">
    <div>Parent Component</div>
    <h2>{{counterName}}</h2>
    <h3>Counter - {{count}}</h3>
    <h3>Counter - {{doubleCount}}</h3>
    <button @click="counterStore.increment">+</button>
    <button @click="counterStore.decrement">-</button>

    <hr>
    <ComponentB/>
    <hr>
    <ComponentC/>
  </div>
</template>

<script setup>

import { storeToRefs } from 'pinia'
import {useCounterStore} from './stores/CounterStore'
import ComponentB from './components/ComponentB.vue'
import ComponentC from './components/ComponentC.vue'

const counterStore = useCounterStore()
const {count,counterName,doubleCount}=storeToRefs(counterStore)

</script>

<style>
.container{
  max-width: 300px ;
  margin: 0 auto;
}
button{
  display: inline-block;
  margin: 0 5px;
  padding: 0 10px;
  font-size: 25px;
}
</style>
