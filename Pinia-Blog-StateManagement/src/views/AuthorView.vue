<template>
  <h1>This is single Author</h1>
  <author :author ="getAuthorByUsername" :posts="getPostPerAuthor(getAuthorByUsername.id)"></author>
</template>

<script setup>
import { computed } from "@vue/runtime-core";
import { storeToRefs } from "pinia";
import { useRoute } from "vue-router";
import { useAuthorStore } from "../stores/author";
import { usePostStore } from "../stores/post";
import Author from '../components/Author.vue'


  const route =useRoute()
  const {authors} = storeToRefs(useAuthorStore())
  const {getPostPerAuthor} = storeToRefs(usePostStore())
  const {fetchPosts} = usePostStore()

  const getAuthorByUsername = computed(()=>{
    return authors.value.find((author)=>author.username === route.params.username)
  })


  fetchPosts()
</script>

<style>

</style>