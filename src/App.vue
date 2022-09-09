<script setup>
import { ref, computed } from "vue"
const counter = ref(0)
const arrayNumbers = ref([])
const increment = () => {
	console.log("Aumentar")
	counter.value++
}
const decrement = () => counter.value--
const reset = () => counter.value = 0
const classCounter = computed(() => {
	if (counter.value === 0) {
		return 'zero'
	}
	if (counter.value > 0) {
		return 'positive'
	}
	if (counter.value < 0) {
		return 'negative'
	}
	return ''
})

const searchArray = computed(() => {
	const exist = arrayNumbers.value.find((number) => number === counter.value)
	if(exist === 0){
		return true
	}
	return exist ? true : false
})
const addToArray = () => {
	arrayNumbers.value.push(counter.value)
}
</script>

<template>
	<h2 :class="classCounter">{{counter}}</h2>
	<button @click="increment">Increment</button>
	<button @click="decrement">Decrement</button>
	<button @click="reset">Reset</button>
	<button @click="addToArray" :disabled="searchArray">Add</button>
	<ul>
		<li v-for="(number, index) in arrayNumbers" :key="index">
			{{number}}
		</li>
	</ul>
</template>

<style>
.positive {
	color: green
}

.negative {
	color: red
}

.zero {
	color: black
}
</style>