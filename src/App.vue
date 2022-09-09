<script setup>
import {ref} from "vue"
const increment = () => {
	console.log("Aumentar")
	counter.value++
}
const counter = ref(0)

</script>

<template>
	<h2>{{counter}}</h2>
	<button @click="increment">Increment</button>
</template>

<style>

</style>