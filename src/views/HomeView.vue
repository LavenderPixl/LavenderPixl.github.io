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
      <InfoBox />
    </div>
    <Sidebar class="sidebar" />
  </div>
</template>

<style scoped>
.container {
}

.infobox {
  padding: 10vw 4vw 0 4vw;
}

.sidebar {
  position: fixed;
  right: 0;
  top: 50%;
}

@media only screen and (min-width: 600px) {
  .container {
    display: flex;
  }

  .infobox {
    padding-top: 10vh;
    padding-left: 40vh;
  }

  .sidebar {
    height: 100%;
    position: fixed;
    top: 40%;
    right: 0;
  }
}
</style>
