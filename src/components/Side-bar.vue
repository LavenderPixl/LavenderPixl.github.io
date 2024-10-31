<template>
  <div class="container">
    <p id="contact">Contact</p>
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
  flex-direction: column;
}

#contact {
  font-size: 3.5vw;
  margin: 0;
}

img {
  height: 8vw;
  margin-top: 2vw;
}

.imgs {
  padding-left: 2vw;
  cursor: pointer;
  width: 10vw;
  background-color: var(--color-background);
  border: 2px solid var(--border-color);
}

@media only screen and (min-width: 769px) {
  .container {
    display: flex;
    flex-direction: column;
  }

  #contact {
    font-size: 1vw;
    margin: 0;
  }

  img {
    height: 2.5vw;
    margin-top: 1vw;
  }

  .imgs {
    cursor: pointer;
    width: 2.5vw;
    margin: 0;
    padding: 0 0.5vw;
    background-color: var(--color-background);
    border: 2px solid var(--border-color);
  }
}
</style>
