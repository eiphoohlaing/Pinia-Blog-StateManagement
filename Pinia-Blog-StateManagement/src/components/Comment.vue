<template>
  <div>
    <div v-for="comment in comments" :key="comment.id">
      <div>
        
        <h3>Comment Name : {{comment.name}}</h3>
        <p>Comment Body : {{comment.body}}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
    defineProps(['comments'])
</script>

<style>

</style>