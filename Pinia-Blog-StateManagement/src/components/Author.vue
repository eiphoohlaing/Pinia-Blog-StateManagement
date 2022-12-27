<template>
  <div>
    <h1>Author Name :{{author.name}}</h1>
    <p>{{posts.length}} posts written</p>
    <p v-for="post in posts " :key="post.id">
        Post Title :
        <RouterLink :to="`/post/${post.id}`">{{post.title}}</RouterLink>
    </p>
  </div>
</template>

<script setup>
    import {RouterLink} from 'vue-router'
    defineProps(['author','posts'])
</script>

<style>

</style>