<script setup>
const emit = defineEmits(["next", "prev"])
defineProps([ "start", "end", "lengthPost"])
</script>

<template>
    <div class="btn-group" role="group" aria-label="Basic example">
        <button @click="emit('prev')"  class="btn btn-outline-primary" :disabled="start === 0">Preovius {{start}}</button>
        <button @click="emit('next')" class="btn btn-outline-primary" :disabled="end >= lengthPost">Next {{end}}</button>
        
    </div>
</template>