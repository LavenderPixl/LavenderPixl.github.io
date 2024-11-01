<script></script>

<template>
  <div id="con">
    <div class="titles">
      <p class="title">Hi, I'm Anna!</p>
      <p class="secondTitle">A Data-technician student.</p>
      <p>Located in Aalborg, DK</p>
    </div>
    <div class="technologies">
      <p id="pTech">Technologies</p>
      <div class="imgs">
        <img src="../assets/c-sharp.png" alt="C#" />
        <!--<a href="https://www.flaticon.com/free-icons/c-sharp" title="c sharp icons">C sharp icons created by manshagraphics - Flaticon</a>-->
        <img src="../assets/python.png" alt="Python" />
        <!--<a href="https://www.flaticon.com/free-icons/python" title="python icons">Python icons created by Nadiinko - Flaticon</a>-->
        <img src="../assets/sql-server.png" alt="SQL" />
        <!--<a href="https://www.flaticon.com/free-icons/sql" title="sql icons">Sql icons created by juicy_fish - Flaticon</a>-->
        <img src="../assets/docker.png" alt="Docker" />
        <!--<a href="https://www.flaticon.com/free-icons/docker" title="docker icons">Docker icons created by Afian Rochmah Afif - Flaticon</a>-->
        <img id="js" src="../assets/javascript.png" alt="JavaScript" />
        <!--<a href="https://www.flaticon.com/free-icons/javascript" title="javascript icons">Javascript icons created by UIUX Mall - Flaticon</a>-->
      </div>
    </div>
    <div class="projectLink">
      <RouterLink to="/projects"> Check out my Projects!</RouterLink>
    </div>
  </div>
</template>

<style scoped>
/*PHONE*/
#con {
  display: flex;
  flex-direction: column;
  justify-content: left;
  border: 2px solid #3a5a40;
  background-color: var(--color-background);

  height: 55vw;
  padding: 3vw;
}

.titles {
  flex-direction: column;
}

.title {
  font-size: 6vw;
  font-weight: bold;
}

.secondTitle {
  font-size: 5vw;
  font-weight: bold;
}

p {
  font-size: 5vw;
  margin: 0;
  padding: 0;
}

.technologies {
  padding-top: 11vw;
  flex-direction: column;
}

.imgs {
  margin-top: 1vw;
  flex-direction: row;
  padding-bottom: 1vw;
}

img {
  padding-left: 2vw;
  padding-right: 2vw;
  height: 13vw;
}

#js {
  padding-right: 0;
}

.projectLink {
  background: var(--btn-color);
  border: 2px solid var(--border-color);
  align-self: center;
  padding: 1vw;
  width: 25vh;
  line-height: 4vh;
  text-align: center;
  z-index: 2;
}

.projectLink a {
  text-decoration-line: underline;
  font-size: 2vh;
  color: var(--color-text);
}

/*PC*/
@media only screen and (min-width: 769px) {
  #con {
    display: flex;
    flex-direction: column;
    justify-content: left;
    border: 2px solid var(--border-color);
    background-color: var(--color-background);

    height: 15vw;
    width: 35vw;
    padding: 1vw;
  }

  .titles {
    flex-direction: column;
  }

  .title {
    font-size: 2vw;
    font-weight: bold;
  }

  .secondTitle {
    font-size: 1.7vw;
    font-weight: bold;
  }

  p {
    font-size: 1.2vw;
    margin: 0;
    padding: 0;
  }

  .technologies {
    padding-top: 3.8vw;
    flex-direction: column;
  }

  .imgs {
    flex-direction: row;
  }

  img {
    padding: 0 0.5vw 0 0;
    height: 3vw;
  }

  .projectLink {
    background: var(--btn-color);
    border: 2px solid var(--border-color);
    width: 15vw;
    padding: 0.5vw 0;
    text-align: center;
    margin-top: -2.5vw;
    margin-left: 30vw;
  }

  .projectLink a {
    text-decoration-line: underline;
    font-size: 1vw;
    color: var(--color-text);
  }
}
</style>
