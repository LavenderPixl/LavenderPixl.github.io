<script>
export default {
  props: {
    name: String,
    description: String,
    url: String,
    updated_at: String
  },
}
</script>

<template>
  <div class="container" @click="$emit('clicked {{this.title}}')">
    <p>{{this.name }}</p>
    <p>{{this.description}}</p>
    <p>{{this.url}}</p>
    <p>{{this.updated_at}}</p>
  </div>
</template>

<style scoped>
.container {
  background: red;
  height: 10vh;
}
</style>
