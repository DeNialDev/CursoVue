<script setup>
 const vueDinamico = 'vue dinamico'
 const styleColor = 'color: blue'
</script>

<template>
	<h1>Hola {{vueDinamico}}</h1>
	<h2 :style="styleColor">Soy azul</h2>
</template>

<style>

</style>