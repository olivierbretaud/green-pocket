<template>
  <div class="container-fluid d-flex flex-column justify-content-center align-items-center">
    <div class="awnser size-anim d-flex justify-content-center flex-column align-items-center" v-if="displayAwnser05">
      <svg id="bg-anim" width="100%" height="100%" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
        <rect x="25" y="84" width="50%" height="2" rx="0.5" ry="0.5" fill="#343a40">
        </rect>
        <image x="25" y="30" height="60%" width="60%"  xlink:href="../assets/moustache.svg" transform="rotate(5)">
          <animateMotion
            path="M 0 0 V 6  Z"
            dur="5s" 
            repeatCount="indefinite" />
        </image>
        <rect x="23" y="85" width="100" height="30" rx="0.5" ry="0.5"  fill="#16b164">
        </rect>
      </svg>

    </div>
      <div class="question d-flex flex-column align-items-center">
        <h5 class="font-weight-bold text-dark question-number" v-if="!displayAwnser05">5/5</h5>  
        <h4 class="font-weight-bold" v-if="goodAwnser05">Bravo!</h4>
        <h4 class="font-weight-bold" v-if="badAwnser05">Mauvaise réponse</h4>
        <h5 class="font-weight-bold text-dark" v-if="displayAwnser05">{{ awnser05 }}</h5>  
        <h5 class="m-3" v-if="!displayAwnser05" >{{ question05 }}</h5>
        <h5 class="m-3" v-if="displayAwnser05" >{{ solution05 }}</h5>
        <div>
        <button type="button" class="custom-button btn btn-light m-2" v-bind:class="{ 'd-none' : displayAwnser05}" v-on:click="displayAwnser05 = true" @click="badAwnser05 = true"> {{ awnserA05 }} </button>
        <button type="button" class="custom-button btn btn-light m-2" v-bind:class="{ 'd-none': displayAwnser05}" v-on:click="displayAwnser05 = true" @click="badAwnser05 = true"> {{ awnserB05 }} </button>
        <button type="button" class="custom-button btn btn-light m-2" v-bind:class="{ 'd-none': displayAwnser05}" v-on:click="displayAwnser05 = true" @click="goodAwnser05 = true"> {{ awnserC05 }} </button>
        <a a href="#06" class="js-scrollTo"><img class="arrows mt-3" src="../assets/arrows.svg" v-if="displayAwnser05" ></a>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Question05',
  data() {
    return {
      question05: "Acheter un smartphone neuf produit autant de CO2 que recharger et utiliser un smartphone pendant ... !",
      solution05: "Avant 10 ans, l'émission de CO2 liée à sa production est plus importante que celle générées par la recharge et l'utilisation quotidienne.",
      awnserA05: '5 ans',
      awnserB05: '7 ans',
      awnserC05: '10 ans',
      awnser05: "Il faut utiliser un smartphone pendant au moins 10 ans",
      displayAwnser05: false,
      goodAwnser05: false,
      badAwnser05: false,
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
  width: 96vw;
  height: 50vh;
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
    width: 96vw;
    height: 50vh;
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
    width: 96vw;
    height: 50vh;
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