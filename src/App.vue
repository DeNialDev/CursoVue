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
	if (exist === 0) {
		return true
	}
	return exist ? true : false
})
const addToArray = () => {
	arrayNumbers.value.push(counter.value)
}
</script>

<template>
	<div class="container text-center mt-5	">

		<h2 :class="classCounter">{{counter}}</h2>
		<div class="btn-group">
			<button @click="increment" class="btn btn-success">Increment</button>
			<button @click="decrement" class="btn btn-danger">Decrement</button>
			<button @click="reset" class="btn btn-secondary">Reset</button>
			<button @click="addToArray" :disabled="searchArray" class="btn btn-primary ">Add</button>
		</div>

		<ul class="list-group mt-3">
			<li class="list-group-item" v-for="(number, index) in arrayNumbers" :key="index">
				{{number}}
			</li>
		</ul>
	</div>

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