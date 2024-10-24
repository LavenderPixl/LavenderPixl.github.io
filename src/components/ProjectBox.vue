<script>
export default {
  props: {
    name: String,
    description: String,
    language: String,
    updated_at: String,
    html_url: String,
  },
  methods: {
    redirect() {
      window.location.href= this.html_url
    }
  }
}
</script>

<template>
  <a @click="redirect()">
    <div class="container">
      <div id="top">
        <p id="name">{{ this.name }}</p>
        <p id="desc">{{ this.description }}</p>
      </div>
      <div id="bottom">
        <p id="language">{{ this.language }}</p>
        <p id="date">{{ this.updated_at }}</p>
      </div>
    </div>
  </a>
</template>

<style scoped>
.container {
  cursor: pointer;
  background: var(--color-background);
  border: var(--border-color) 2px solid;
  display: flex;
  flex-direction: column;
  justify-content: left;
  padding-left: 1vw;
  padding-right: 1vw;
}

#top {
  display: flex;
  flex-direction: column;
}

#name {
  margin-top: 1vw;
  margin-bottom: 0;
  font-size: 1.2vw;
  text-decoration: underline;
}

#desc {
  font-size: 1vw;
  height: 3vw;
}

#bottom {
  //height: 3vw;
  display: flex;
}

#bottom p {
  width: 100%;
  margin: 0 0 1vw 0;
  //margin-bottom: 1vw;
}

#language {
  text-align: left;
  font-size: 1vw;
}

#date {
  text-align: right;
  font-size: 1vw;
}

a {
  text-decoration-line: none;
  color: var(--color-text);
}
</style>
