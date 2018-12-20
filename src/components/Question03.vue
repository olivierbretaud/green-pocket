<template>
  <div class="container-fluid d-flex flex-column justify-content-center align-items-center">
    <div class="awnser size-anim" v-if="displayAwnser03">
      <svg id="bg-anim" width="100%" height="100%" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
        <ellipse cx="50" cy="80" rx="50" ry="10" stroke="wihte" stroke-width="1" fill="#a4c9d6" />
          <image x="50" y="20" height="25%" width="25%"  xlink:href="../assets/skull-crossbones.svg" >
            <animateMotion
              path="M 0 0 V 8 Z"
              dur="5s"
              repeatCount="indefinite" />
          </image>
          <image x="28" y="30" height="15%" width="15%"  xlink:href="../assets/skull-crossbones.svg" >
            <animateMotion
              path="M 0 0 V 4 Z"
              dur="3s"
              repeatCount="indefinite" />
          </image>
        <image x="57" y="-63" height="40%" width="40%" xlink:href="../assets/phone.svg" transform="rotate(85)">
          <animateMotion
            path="M 0 0 V 2 Z"
            dur="2s" 
            repeatCount="indefinite" />
        </image>
          <rect x="30" y="80" width="45" height="8" fill="#a4c9d6" />
      </svg>
    </div>
    <div class="question d-flex flex-column align-items-center">
      <h5 class="font-weight-bold text-dark question-number" v-if="!displayAwnser03">3/5</h5>  
      <h4 class="font-weight-bold" v-if="goodAwnser03">Bravo!</h4>
      <h4 class="font-weight-bold" v-if="badAwnser03">Mauvaise réponse</h4>
      <h5 class="font-weight-bold text-dark" v-if="displayAwnser03">{{ awnser03 }}</h5>  
      <h5 class="m-3" v-if="!displayAwnser03" >{{ question03 }}</h5>
      <h5 class="m-3" v-if="displayAwnser03" >{{ solution03 }}</h5>
      <div>
        <button type="button" class="custom-button btn btn-light m-2" v-bind:class="{ 'd-none' : displayAwnser03}" v-on:click="displayAwnser03 = true" @click="badAwnser03 = true"> {{ awnserA03 }} </button>
        <button type="button" class="custom-button btn btn-light m-2" v-bind:class="{ 'd-none': displayAwnser03}" v-on:click="displayAwnser03 = true" @click="badAwnser03 = true"> {{ awnserB03 }} </button>
        <button type="button" class="custom-button btn btn-light m-2" v-bind:class="{ 'd-none': displayAwnser03}" v-on:click="displayAwnser03 = true" @click="goodAwnser03 = true"> {{ awnserC03 }} </button>
        <a a href="#04" class="js-scrollTo"><img class="arrows mt-3" src="../assets/arrows.svg" v-if="displayAwnser03" ></a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Question03',
  data() {
    return {
      question03: "les aimants de nos smartphones sont constituées de néodyme. Combien de litres d'eau pollués sont rejetés pour la production d'une tonne de néodyme?",
      solution03: "La production de néodyme génère de grandes quantités de déchets, ce qui est d’autant plus dramatique que ces derniers sont particulièrement nocifs",
      awnserA03: '25 000 litres',
      awnserB03: '50 000 litres',
      awnserC03: '75 000 litres',
      awnser03: "75 000 litres d'eau par tonne de néodyme",
      displayAwnser03: false,
      goodAwnser03: false,
      badAwnser03: false,
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
