<script>
import ProjectBox from '@/components/ProjectBox.vue'

export default {
  components: { ProjectBox },
  mounted() {
    // this.getRepos()
  },
  data() {
    return {
      currentPage: 1,
      repos: [],
      repo: {
        name: '',
        description: '',
        url: '',
        updated_at: ''
      }
    }
  },
  methods: {
    // async getRepos() {
    //   const res = await fetch('https://api.github.com/users/LavenderPixl/repos')
    //   const projects = await res.json()
    //   for (let project of projects) {
    //     this.repos.push(project)
    //   }
    // },
    // pager(btnClicked) {
    //   let page = btnClicked
    //
    //    btnClicked
    //   if page
    // }
  }
}
</script>

<template>
  <div v-for="(repo, index) in repos" :key="index">
    <ProjectBox
      :name="repo.name"
      :description="repo.description"
      :url="repo.url"
      :updated_at="repo.updated_at"
    ></ProjectBox>
  </div>

  <div class="pager">
<!--    <button @click="pager(0)"></button>
    <button @click="pager(1)"></button>-->
  </div>
</template>

<style>
</style>
