<script setup>
import BlogPost from './components/BlogPost.vue'
import { ref, onMounted } from 'vue'
import PaginatePost from './components/PaginatePost.vue';
import LoadingSpinner from './components/LoadingSpinner.vue';
const posts = ref([])
const favorite = ref('')
const posXpage = 10
const start = ref(0)
const end = ref(posXpage)
const onLoading = ref(false)
const setFavorite = (title) => {
	favorite.value = title
}
const next = () => {
	start.value = start.value + posXpage
	end.value = end.value + posXpage
}

const prev = () => {
	start.value = start.value - posXpage
	end.value = end.value - posXpage
}
onMounted(async () => {
	onLoading.value = true
	try {
		const response = await fetch('https://jsonplaceholder.typicode.com/posts')
		posts.value = await response.json()
	} catch (error) {
		console.log(error)
	} finally {
		onLoading.value = false
	}
})

</script>

<template>
	<LoadingSpinner v-if="onLoading" />
	<div class="container">
		<h2>Post favorito: {{favorite}}</h2>

		<PaginatePost @next="next" @prev="prev" class="mb-2" :start="start" :end="end" :lengthPost="posts.length" />

		<BlogPost class="mb-2" v-for="post in posts.slice(start, end)" :key="post.title" :title="post.title"
			:id="post.id" :body="post.body" @setFavorite="setFavorite" />
	</div>
</template>