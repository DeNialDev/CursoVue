<script setup>

const Fruits = {
		name: "Fresa",
		price: "$1.00",
		description: "Una fresa"
	}
</script>

<template>
	<ul>
		<li v-for="(value, prop) in Fruits" :key="value">
			{{prop}} - {{value}}
		</li>
	</ul> 
</template>

<style>

</style>