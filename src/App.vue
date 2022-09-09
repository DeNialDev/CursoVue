<script setup>

const Fruits = [
	{
		name: "Fresa",
		price: "$1.00",
		description: "Una fresa",
		stock: 0,
	},
	{
		name: "Melon",
		price: "$1.00",
		description: "Una Melon",
		stock: 30,
	},

]



</script>

<template>
	<ul>
		<template v-for="item in Fruits" :key="item.name">
			<li v-if="item.stock > 5">
			
				{{item.name}} - {{item.price}}
			
		</li>
		</template>
		
	</ul>
</template>

<style>

</style>