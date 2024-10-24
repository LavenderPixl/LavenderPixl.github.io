<script>
import ProjectBox from '@/components/ProjectBox.vue'
import axios from 'axios'

export default {
  components: { ProjectBox },
  data() {
    return {
      currentPage: 1,
      // displaying: 9,
      repos: [],
      repo: {
        name: '',
        description: '',
        language: '',
        updated_at: '',
        html_url: '',
      },
      displaying: [],
    }
  },
  async mounted() {
    await this.getRepos()
  },
  methods: {
    async getRepos() {
      await axios
        .get('https://api.github.com/users/LavenderPixl/repos', {
          headers: {
            'User-Agent': 'LavenderPixl',
            Authorization: `Bearer ${import.meta.env.GITHUB_TOKEN}`,
          },
        })
        .then(res => {
          // const projects = res.json
          for (let project of res.data) {
            this.repos.push(project)
          }

          this.repos.sort(
            (a, b) => Date.parse(a.updated_at) - Date.parse(b.updated_at),
          )
          this.repos.reverse()

          this.displaying = this.repos.slice(0, 9)
        })
    },

    pager(btnClicked) {
      if (btnClicked === '-') {
        if (this.currentPage > 1) {
          this.displaying.pop()
          this.currentPage--
        } else return
      }
      if (btnClicked === '+' && this.currentPage < this.repos.length / 9) {
        this.displaying.pop()
        this.currentPage++
      }

      let start = this.getStart()
      this.displaying = this.repos.slice(start, start + 9)
    },
    getStart() {
      let start = (this.currentPage - 1) * 9
      Math.round(start)
      return start
    },
  },
}
</script>

<template>
  <div id="wrapper">
    <!--    <SideBar />-->
    <div id="topBar">
      <RouterLink to="/" id="back"> &lt; Back to Home</RouterLink>
      <p id="topLine">Click a project to view it on Github.</p>
    </div>
    <div class="repos">
      <ProjectBox
        v-for="(repo, index) in displaying"
        :key="index"
        :name="repo.name"
        :description="repo.description"
        :language="repo.language"
        :updated_at="repo.updated_at"
        :html_url="repo.html_url"
      ></ProjectBox>
    </div>
    <div id="pager">
      <button @click="pager('-')" id="btn">&lt;</button>
      <p id="pageNumber">{{ this.currentPage }}</p>
      <button @click="pager('+')" id="btn">&gt;</button>
    </div>
  </div>
</template>

<style>
#wrapper {
  width: 100%;
  display: flex;
  overflow: scroll;
  flex-direction: column;
}

#topBar {
  width: 100%;
  margin-top: 2vw;
  margin-bottom: 1vw;
  font-size: 1vw;
  display: flex;
  flex-direction: row;
}

#topLine {
  width: 100%;
  margin-top: 0;
}

#back {
  width: 70%;
  color: var(--color-text);
  margin-left: 2%;
  text-decoration: underline;
}
.repos {
  justify-content: center;
  display: grid;
  grid-template-columns: 25vw 25vw 25vw;
  column-gap: 4vw;
  grid-template-rows: 10vw 10vw 10vw;
  row-gap: 4vw;
}

#pager {
  width: 100%;
  display: flex;
  justify-content: center;
  margin-top: 2vw;
}

#btn {
  height: 1.5vw;
  width: 3vw;
  font-size: 1vw;
  border: var(--border-color) 2px solid;
  background-color: #a3b18a;
  cursor: pointer;
}

#pageNumber {
  margin-left: 1vw;
  margin-right: 0.4vw;
  margin-top: 0;
  font-size: 1vw;
  width: 1vw;
  text-decoration: underline;
  //margin: 0;
}
</style>
