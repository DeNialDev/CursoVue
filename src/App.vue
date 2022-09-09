<script setup>
import BlogPost from './components/BlogPost.vue'
import {ref} from 'vue'
const posts = ref([]);
const favorite = ref('')
const setFavorite = (title) =>{
	favorite.value = title
}

fetch('https://jsonplaceholder.typicode.com/posts')
.then(res => res.json())
.then((data) => posts.value = data)

</script>

<template>
	<div class="container">
		<h2>Post favorito: {{favorite}}</h2>
		<BlogPost v-for="post in posts" :key="post.title" :title="post.title" 
		:id="post.id" :body="post.body" @setFavorite="setFavorite" 
		/>
	</div>
</template>