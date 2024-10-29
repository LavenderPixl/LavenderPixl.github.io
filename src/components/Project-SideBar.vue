<template>
  <div class="container">
    <div class="imgs">
      <img
        src="../assets/github.png"
        alt="Github"
        @click="redirect('https://github.com/LavenderPixl')"
      />
      <!--      https://www.flaticon.com/free-icon/github_3291695?term=github&page=1&position=1&origin=search&related_id=3291695-->
      <img
        src="../assets/linkedin.png"
        alt="LinkedIn"
        @click="
          redirect('https://www.linkedin.com/in/anna-jacobsen-147783236/')
        "
      />
      <!--      https://www.flaticon.com/free-icon/linkedin_3536569?term=linkedin&page=1&position=2&origin=search&related_id=3536569-->
      <a href="mailto:annajacobsen1999@hotmail.com">
        <img src="../assets/email.png" alt="Email" />
      </a>
      <!--      <a href="https://www.flaticon.com/free-icons/email" title="email icons">Email icons created by Freepik - Flaticon</a>-->
    </div>
  </div>
</template>

<script>
export default {
  name: 'SideBar',
  methods: {
    redirect(link) {
      window.location.href = link
    },
  },
}
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: row;
  width: 100%;
}

img {
  height: 8vw;
  margin-right: 5vw;
  cursor: pointer;
}

.imgs {
  padding: 0;
  margin: 0;
}

@media only screen and (min-width: 769px) {
  .container {
    display: flex;
    flex-direction: column;
    width: 100%;
  }

  img {
    height: 2.5vw;
    right: 0;
    margin-top: 1vw;
    margin-right: 0;
  }

  .imgs {
    cursor: pointer;
    width: 2.5vw;
    margin: 0;
    padding: 0 0.5vw;
    background-color: #dad7cd;
    align-items: flex-end;
    justify-content: flex-end;
    border: 2px solid #3a5a40;
  }
}
</style>
