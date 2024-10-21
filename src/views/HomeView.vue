<script setup>
import Sidebar from '@/components/Side-bar.vue'
import InfoBox from '@/components/InfoBox.vue'
</script>

<template>
  <div class="container">
    <InfoBox class="infobox" />
    <Sidebar class="sidebar" />
  </div>
</template>

<style scoped>

.container {
  display: flex;
}
.infobox {
  align-self: center;
}

.sidebar {
  height: 100%;
  position: fixed;
  top: 40%;
  right: 0;
}
</style>
