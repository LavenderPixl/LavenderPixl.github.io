<script setup></script>

<template>
  <div class="container">
    <div class="titles">
      <p class="title">Hi, I'm Anna!</p>
      <p class="title">A Data-technician student.</p>
      <p> Located in Aalborg, DK </p>
    </div>
    <div class="technologies">
      <p>Technologies</p>
      <div class="imgs">
        <img src="../assets/c-sharp.png" alt="C#"/>
        <!--<a href="https://www.flaticon.com/free-icons/c-sharp" title="c sharp icons">C sharp icons created by manshagraphics - Flaticon</a>-->
        <img src="../assets/python.png" alt="Python"/>
        <!--<a href="https://www.flaticon.com/free-icons/python" title="python icons">Python icons created by Nadiinko - Flaticon</a>-->
        <img src="../assets/sql-server.png" alt="SQL"/>
        <!--<a href="https://www.flaticon.com/free-icons/sql" title="sql icons">Sql icons created by juicy_fish - Flaticon</a>-->
        <img src="../assets/docker.png" alt="Docker"/>
        <!--<a href="https://www.flaticon.com/free-icons/docker" title="docker icons">Docker icons created by Afian Rochmah Afif - Flaticon</a>-->
        <img src="../assets/javascript.png" alt="JavaScript"/>
        <!--<a href="https://www.flaticon.com/free-icons/javascript" title="javascript icons">Javascript icons created by UIUX Mall - Flaticon</a>-->
      </div>
    </div>
    <div class="projectLink">
      <a> Check out my Projects!</a>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: left;
  border: 2px solid #3a5a40;
  background-color: #dad7cd;

  height: 27vh;
  width: 65vh;
  //min-height: 230px;
  padding: 2vh;
}

.titles {
  flex-basis: 100%;
  flex-direction: column;
}

.title {
  font-size: 4vh;
  font-weight: bold;
}

p {
  font-size: 2.5vh;
  margin: 0;
  padding: 0;
}

.technologies {
  padding-top: 7vh;
  flex-direction: column;
}

.imgs {
  flex-direction: row;
  padding-bottom: 1vh;
}

img {
  height: 5vh;
}

.projectLink {
  background: #A3B18A;
  border: 2px solid #3a5a40;
  align-self: flex-end;
  width: 25vh;
  //min-height: 50px;
  line-height: 4vh;
  text-align: center;
  text-decoration-line: underline;
}

.projectLink a {
  font-size: 2vh;
  width: 20vh;
}

</style>

<!--
.container {
  display: flex;
  flex-direction: column;
  border: 2px solid #3a5a40;
  background-color: #dad7cd;
  min-height: 21vh;
  height: 23vh;
  padding: 2vh;
}

.title {
  font-size: 36px;
  font-weight: bold;
}

p {
  margin: 0;
  padding: 0;
}

.technologies {
  margin-top: 70px;
}

.imgs {
  margin-top: 1vh;
}

img {
  height: 50px;
  margin-right: 10px;
}

.projectLink {
  background: #A3B18A;
  border: 2px solid #3a5a40;
  //align-self: flex-end;
  width: 220px;
  min-height: 50px;
  line-height: 50px;
  text-align: center;
  text-decoration-line: underline;
}
-->

