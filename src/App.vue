<script setup>
import BlogPost from './components/BlogPost.vue'
import {ref} from 'vue'
const posts = ref([
	{ id: 1, title: "Post 01", body: "Descrión del post 01" },
	{ id: 2, title: "Post 02", body: "Descrión del post 02" },
	{ id: 3, title: "Post 03" },
]);
const favorite = ref('')
const setFavorite = (title) =>{
	favorite.value = title
}
</script>

<template>
	<div class="container">
		<h2>Post favorito: {{favorite}}</h2>
		<BlogPost v-for="post in posts" :key="post.title" :title="post.title" 
		:id="post.id" :body="post.body" @setFavorite="setFavorite" 
		/>
	</div>
</template>