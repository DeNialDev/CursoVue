<script setup>
 const vueDynamic = 'vue dinamico'
 const styleColor = 'color: blue'
 const isActive = true
</script>

<template>
	<h1>Hola {{vueDynamic}}</h1>
	<h2 :style="styleColor">Soy azul</h2>
	<h2 v-if="isActive">Estoy activo</h2>
	<p v-if="!isActive">Estoy inactivo</p> 
	<h2 v-show="isActive">Estoy activo</h2>
</template>

<style>

</style>