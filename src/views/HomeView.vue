<script>
import Sidebar from '@/components/Side-bar.vue'
import InfoBox from '@/components/InfoBox.vue'
import { defineComponent } from 'vue'

export default defineComponent({
  components: { InfoBox, Sidebar },
})
</script>

<template>
  <div class="container">
    <div class="infobox">
      <InfoBox/>
    </div>
    <Sidebar class="sidebar"/>
  </div>
</template>

<style scoped>
.container {
  display: flex;
}

.infobox {
  margin-top: 20vh;
  margin-left: 50vh;
}

.sidebar {
  height: 100%;
  position: fixed;
  top: 40%;
  right: 0;
}
</style>
