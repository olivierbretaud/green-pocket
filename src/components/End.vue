<template>
  <div class="container-fluid d-flex flex-column justify-content-center align-items-center">
    <div class="question d-flex flex-column align-items-center">
      <h5 class="m-3" >{{ endSentence }}</h5>
      <h5 class="font-weight-bold text-dark" >{{ mainSentence }}</h5>
    </div>
  </div>
</template>

<script>
export default {
  name: 'End',
  data() {
    return {
      endSentence: "Nos téléphones ont un impact considérable sur l'environement!",
      mainSentence: "Faites un geste pour la planète, conserver votre téléphone !"
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container-fluid {
  min-height: 100vh;
  padding: 0;
}

.question {
  max-width: 600px;
  margin: 10px;
}

.awnser {
  width: 100vw;
  height: 60vh;
}

#bg-amin {
  position: absolute;
  z-index: -1;
}

#illustre {
  position: relative;
  z-index: 1
}

.size-anim {
  -moz-animation-name: main; /* Safari 4.0 - 8.0 */
  -moz-animation-duration: 1s; /* Safari 4.0 - 8.0 */
  animation-name: main;
  animation-duration: 1s;
}

/* Safari 4.0 - 8.0 */
@-moz-keyframes main {
  from {
    width: 0vw;
    height: 0vh;
    opacity: 0;
  }
  to {
    width: 100vw;
    height: 60vh;
    opacity: 1;
  }
}

/* Standard syntax */
@keyframes main {
  from {
    width: 0vw;
    height: 0vh;
    opacity: 0;
  }
  to {
    width: 100vw;
    height: 60vh;
    opacity: 1;
  }
}

ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
