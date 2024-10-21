<template>
  <div class="container">
    <p>Contact</p>
    <div class="imgs">
      <img src="../assets/github.png" alt="Github" />
      <!--      https://www.flaticon.com/free-icon/github_3291695?term=github&page=1&position=1&origin=search&related_id=3291695-->
      <img src="../assets/linkedin.png" alt="LinkedIn" />
      <!--      https://www.flaticon.com/free-icon/linkedin_3536569?term=linkedin&page=1&position=2&origin=search&related_id=3536569-->
      <img src="../assets/email.png" alt="Email" />
      <!--      <a href="https://www.flaticon.com/free-icons/email" title="email icons">Email icons created by Freepik - Flaticon</a>-->
    </div>
  </div>
</template>

<script>
export default {
  name: 'SideBar',
}
</script>

<style scoped>
.container {
  flex-direction: column;
  display: flex;
  align-items: center;
  //margin: auto 0;
}

p {
  font-size: 2vh;
  margin: 0;
}

img {
  height: 5vh;
  margin-top: 1vh;
}

.imgs {
  background-color: #dad7cd;
  width: 5vh;
  padding: 1vh;
  //padding: 0 15px 0 15px;
  border: 2px solid #3a5a40;
}
</style>
