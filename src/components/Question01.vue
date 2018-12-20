<template>
  <div class="container-fluid d-flex flex-column justify-content-center align-items-center">
    <div class="awnser size-anim" v-if="displayAwnser">
      <svg id="bg-anim" width="100%" height="100%" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
        <rect id="a" x="-2" y="6" width="10" height="1" rx="0.5" ry="0.5" fill="#000" >
          <animateMotion
            path="M 0 0 H 300"
            dur="3s"
            repeatCount="indefinite" />
        </rect>
        <circle cx="50" cy="50" r="40" fill="#000" style="fill-opacity: .10;"/>
        <image id="phone" x="15" y="15" height="70%" width="70%"  xlink:href="../assets/phone.svg" >
          <animateMotion
            path="M 0 0 V 10  Z"
            dur="5s" 
            repeatCount="indefinite" />
        </image>
      </svg>
    </div>
    <div class="question d-flex flex-column align-items-center">
      <h4 class="font-weight-bold" v-if="goodAwnser">Bravo!</h4>
      <h4 class="font-weight-bold" v-if="badAwnser">Mauvaise réponse</h4>
      <h5 class="m-3" v-if="!displayAwnser" >{{ question }}</h5>
      <h5 class="m-3" v-if="displayAwnser" >{{ solution }}</h5>
      <div>
        <button type="button" class="btn btn-light m-2" v-bind:class="{ 'd-none' : displayAwnser}" v-on:click="displayAwnser = true" @click="goodAwnser = true"> {{ awnserA }} </button>
        <button type="button" class="btn btn-light m-2" v-bind:class="{ 'd-none': displayAwnser}" v-on:click="displayAwnser = true" @click="badAwnser = true"> {{ awnserB }} </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Question01',
  data() {
    return {
      question: 'La pollution issue de l’usage d’un téléphone est elle plus importante que celle issue de sa fabrication ?',
      solution: "La pollution issue de la production un téléphone est bien plus importante, l’extraction des minerais qui le composent à impact considérable sur l’environnement",
      awnserA: 'oui',
      awnserB: 'non',
      displayAwnser: false,
      goodAwnser: false,
      badAwnser: false,
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
