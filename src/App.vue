<script setup>
import {ref} from "vue"
const counter = ref(0)
const increment = () => {
	console.log("Aumentar")
	counter.value++
}
const decrement = () => counter.value--
const reset = () => counter.value = 0


</script>

<template>
	<h2 :class="counter > 0 ? 'positive' : 'negative' ">{{counter}}</h2>
	<button @click="increment">Increment</button>
	<button @click="decrement">Decrement</button>
	<button @click="reset">Reset</button>
</template>

<style>
.positive{
	color: green
}
.negative{
	color: red
}
</style>