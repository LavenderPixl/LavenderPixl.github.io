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
  //display: flex;
}

.infobox {
  margin: 10vw 4vw 0 4vw;

  //display: flex;
}

.sidebar {
  position: fixed;
  right: 0;
  top: 65%;
}

@media only screen and (min-width: 768px) {
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
}
</style>
