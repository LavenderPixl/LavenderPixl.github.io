<script>
export default {
  props: {
    name: String,
    description: String,
    language: String,
    updated_at: String,
    html_url: String,
  },
  async mounted() {
    await this.clean()
  },
  methods: {
    redirect() {
      window.location.href = this.html_url
    },
    async clean() {
      // this.updated_at = this.updated_at.slice(0, 11)
    },
  },
}
</script>

<template>
  <div class="container">
    <a @click="redirect()">
      <div id="top">
        <p id="name">{{ this.name }}</p>
        <p id="desc">{{ this.description }}</p>
      </div>
      <div id="bottom">
        <p id="language">{{ this.language }}</p>
        <p id="date">{{ this.updated_at.slice(0, 10) }}</p>
      </div>
    </a>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  cursor: pointer;
  background: var(--color-background);
  border: var(--border-color) 2px solid;
  justify-content: left;
  padding-left: 3vw;
  padding-right: 3vw;
  height: 35vw;
  width: 80vw;
}

#top {
  display: flex;
  flex-direction: column;
}

#name {
  margin-top: 1vw;
  margin-bottom: 0;
  font-size: 5vw;
  text-decoration: underline;
}

#desc {
  margin-top: 2vw;
  margin-bottom: 0;
  height: 20vw;
  font-size: 4vw;
}

#bottom {
  height: 5vw;
  display: flex;
  flex-direction: row;
}

#bottom p {
  width: 100%;
}

#language {
  margin: 0;
  text-align: left;
  font-size: 3.5vw;
}

#date {
  margin: 0;
  text-align: right;
  font-size: 3.5vw;
}

a {
  text-decoration-line: none;
  color: var(--color-text);
}

@media only screen and (min-width: 769px) {
  .container {
    cursor: pointer;
    background: var(--color-background);
    border: var(--border-color) 2px solid;
    display: flex;
    flex-direction: column;
    justify-content: left;
    padding-left: 1vw;
    padding-right: 1vw;
    width: 20vw;
    height: 10vw;
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
    margin-top: 0.5vw;
    font-size: 1vw;
    height: 5vw;
  }

  #bottom {
    height: 1.5vw;
    display: flex;
  }

  #bottom p {
    width: 100%;
    margin: 0 0 1vw 0;
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
}
</style>
