<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template class="app-container">
  <header>
<!--    <nav>-->
<!--      <RouterLink to="/">Home</RouterLink>-->
<!--      <RouterLink to="/projects">Projects</RouterLink>-->
<!--    </nav>-->
    <!--    <img-->
<!--      alt="Vue logo"-->
<!--      class="logo"-->
<!--      src="@/assets/logo.svg"-->
<!--      width="125"-->
<!--      height="125"-->
<!--    />-->
  </header>

  <RouterView />
</template>

<style scoped>
.app-container {
}


nav {
  width: 100%;
}
</style>
