<script>
</script>

<template>
  <div id="clouds">
    <img id="cloud1" src="@/assets/Cloud1.png" alt="Cloud" />
    <img id="cloud2" src="@/assets/Cloud2.png" alt="Cloud" />
    <img id="cloud3" src="@/assets/Cloud3.png" alt="Cloud" />
  </div>
</template>

<style scoped>
#clouds {
  bottom: 0;
  left: 0;
  right: 0;
  top: 0;
  position: absolute;
  width: 100%;
  overflow: hidden;
}

#cloud1 {
  -webkit-animation: animateCloud 35s linear infinite;
  -moz-animation: animateCloud 35s linear infinite;
  animation: animateCloud 35s linear infinite;
  position: absolute;
  left: -50vw;
  bottom: 125vw;
  z-index: -1;

  -webkit-transform: scale(0.4);
  -moz-transform: scale(0.4);
  transform: scale(0.4);
}

#cloud2 {
  -webkit-animation: animateCloud 20s linear infinite;
  -moz-animation: animateCloud 20s linear infinite;
  animation: animateCloud 20s linear infinite;
  position: absolute;
  left: -70vw;
  bottom: 20vw;

  -webkit-transform: scale(0.4);
  -moz-transform: scale(0.4);
  transform: scale(0.4);
}

#cloud3 {
  -webkit-animation: animateCloud 40s linear infinite;
  -moz-animation: animateCloud 40s linear infinite;
  animation: animateCloud 40s linear infinite;
  position: absolute;
  bottom: 75vw;
  left: -60vw;


  -webkit-transform: scale(0.4);
  -moz-transform: scale(0.4);
  transform: scale(0.4);
}

@-webkit-keyframes animateCloud {
  from {
    margin-left: -20vw;
  }
  to {
    margin-left: 150%;
  }
}

@-moz-keyframes animateCloud {
  from {
    margin-left: -20vw;
  }
  to {
    margin-left: 150%;
  }
}

@keyframes animateCloud {
  from {
    margin-left: -20vw;
  }
  to {
    margin-left: 150%;
  }
}

@media only screen and (min-width: 769px) {
  #clouds {
    bottom: 0;
    left: 0;
    right: 0;
    top: 0;
    position: absolute;
    width: 100%;
    overflow: hidden;
  }

  #cloud1 {
    -webkit-animation: animateCloud 45s linear infinite;
    -moz-animation: animateCloud 45s linear infinite;
    animation: animateCloud 45s linear infinite;
    position: absolute;
    left: -30vw;
    bottom: 19vw;
    z-index: 0;
    -webkit-transform: scale(0.6);
    -moz-transform: scale(0.6);
    transform: scale(0.6);
  }

  #cloud2 {
    -webkit-animation: animateCloud 35s linear infinite;
    -moz-animation: animateCloud 35s linear infinite;
    animation: animateCloud 35s linear infinite;
    position: absolute;
    left: -20vw;
    bottom: 7vw;

    -webkit-transform: scale(0.7);
    -moz-transform: scale(0.7);
    transform: scale(0.7);
  }

  #cloud3 {
    -webkit-animation: animateCloud 55s linear infinite;
    -moz-animation: animateCloud 55s linear infinite;
    animation: animateCloud 55s linear infinite;
    position: absolute;
    bottom: 33vw;
    left: -10vw;
    z-index: -1;

    -webkit-transform: scale(0.5);
    -moz-transform: scale(0.5);
    transform: scale(0.5);
  }

  @-webkit-keyframes animateCloud {
    from {
      margin-left: -10vw;
    }
    to {
      margin-left: 100%;
    }
  }

  @-moz-keyframes animateCloud {
    from {
      margin-left: -10vw;
    }
    to {
      margin-left: 100%;
    }
  }

  @keyframes animateCloud {
    from {
      margin-left: -10vw;
    }
    to {
      margin-left: 120%;
    }
  }
}
</style>
