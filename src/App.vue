<script setup>

const arrayFruits = ["Apple", "Orange", "Watermelon", "Grapes"]
</script>

<template>
	<ul>
		<li v-for="(fruit, index) in arrayFruits"
		:key="index">
			{{index}} - {{fruit}}
		</li>
	</ul>
</template>

<style>

</style>