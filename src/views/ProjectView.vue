<script>
import ProjectBox from '@/components/ProjectBox.vue'
import axios from 'axios'
import ProjectSideBar from '@/components/Project-SideBar.vue'

export default {
  components: { ProjectSideBar, ProjectBox },
  data() {
    return {
      currentPage: 1,
      amountShown: 9,
      maxPage: 1,
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
    isMobile() {
      return /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(
        navigator.userAgent,
      )
        ? (this.amountShown = 3)
        : (this.amountShown = 9)
    },

    async getRepos() {
      await axios
        .get('https://api.github.com/users/LavenderPixl/repos')
        .then(res => {
          for (let project of res.data) {
            this.repos.push(project)
          }

          this.repos.sort(
            (a, b) => Date.parse(a.updated_at) - Date.parse(b.updated_at),
          )
          this.repos.reverse()

          this.isMobile()
          this.displaying = this.repos.slice(0, this.amountShown)
          this.maxPage = Math.ceil(this.repos.length / this.amountShown)
        })
    },

    pager(btnClicked) {
      if (btnClicked === '-') {
        if (this.currentPage > 1) {
          this.displaying.pop()
          this.currentPage--
        } else return
      }
      if (
        btnClicked === '+' &&
        this.currentPage < this.repos.length / this.amountShown
      ) {
        this.displaying.pop()
        this.currentPage++
      }

      let start = this.getStart()
      this.displaying = this.repos.slice(start, start + this.amountShown)
    },
    getStart() {
      let start = (this.currentPage - 1) * this.amountShown
      Math.round(start)
      return start
    },
  },
}
</script>

<template>
  <div id="wrapper">
    <div id="topBar">
      <RouterLink to="/" id="back"> &lt; Back to Home</RouterLink>
      <p id="topLinePC">Click a project to view it on Github.</p>
      <Project-SideBar id="bar" />
    </div>
    <p id="topLine">Click a project to view it on Github.</p>
    <div class="repos">
      <ProjectBox
        id="projectBox"
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
      <p id="pageNumber">{{ this.currentPage }} / {{ this.maxPage }}</p>
      <button @click="pager('+')" id="btn">&gt;</button>
    </div>
  </div>
</template>

<style>
#wrapper {
  width: 100%;
  display: flex;
  flex-direction: column;
}

#topBar {
  display: inline-flex;
  flex-direction: row;
  justify-content: left;
  border-bottom: 4px dotted var(--border-color);
  background-color: #dad7cd;
  width: 100%;
  height: 10vw;
  padding-bottom: 4vw;
}

#back {
  width: 35%;
  height: 5vw;
  padding-top: 5vw;
  align-self: flex-start;
  margin-left: 2vw;
  font-size: 4vw;
  text-decoration: underline;
  color: var(--color-text);
}

#bar {
  justify-content: flex-end;
  margin-left: 23vw;
  width: 40%;
  margin-top: 4vw;
  right: 0;
  margin-right: 0;
  position: relative;
}

#topLine {
  margin-top: 10vw;
  align-self: center;
  font-size: 5vw;
}

#topLinePC {
  display: none;
  align-self: center;
  font-size: 5vw;
}

.repos {
  align-items: center;
  width: 100%;
  display: flex;
  flex-direction: column;
}

#projectBox {
  padding-bottom: 15vw;
}

#pager {
  width: 100%;
  display: flex;
  justify-content: center;
  bottom: 0;
  padding-bottom: 3vw;
}

#btn {
  height: 10vw;
  width: 10vw;
  font-size: 5vw;
  border: var(--border-color) 2px solid;
  background-color: var(--btn-color);
  cursor: pointer;
}

#pageNumber {
  margin-left: 4vw;
  margin-top: 1vw;
  width: 15vw;
  font-size: 5vw;
  text-decoration: underline;
}

@media only screen and (min-width: 769px) {
  #wrapper {
    width: 100%;
    display: flex;
    flex-direction: column;
  }

  #topBar {
    display: flex;
    flex-direction: row;
    justify-content: left;
    width: 100%;
    height: 4vw;
    padding: 0;
    border-bottom: 0;
  }

  #back {
    width: 11%;
    height: auto;
    padding-top: 1vw;
    align-self: flex-start;
    margin-left: 1vw;
    font-size: 1.3vw;
    text-decoration: underline;
    color: var(--color-text);
  }

  #bar {
    margin-left: 0;
    width: 3.9%;
    margin-top: 30vw;
  }

  #topLine {
    display: none;
    align-self: center;
    font-size: 1.3vw;
  }

  #topLinePC {
    width: 58%;
    display: flex;
    margin-left: 28vw;
    font-size: 1.2vw;
  }

  .repos {
    justify-content: center;
    display: grid;
    grid-template-columns: 25vw 25vw 25vw;
    column-gap: 4vw;
    grid-template-rows: 10vw 10vw 10vw;
    row-gap: 4vw;
  }

  #projectBox {
    padding-bottom: 0;
  }

  #btn {
    height: 2vw;
    width: 3vw;
    font-size: 1vw;
    border: var(--border-color) 2px solid;
    background-color: var(--btn-color);
    cursor: pointer;
  }

  #pageNumber {
    margin-left: 1vw;
    margin-right: 1vw;
    margin-top: 0.3vw;
    width: auto;
    font-size: 1.3vw;
    text-decoration: underline;
  }

  #pager {
    margin-top: 1vw;
    padding: 0;
  }
}
</style>
