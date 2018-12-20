<template>
  <div class="container-fluid d-flex flex-column justify-content-center align-items-center">
    <div class="awnser size-anim" v-if="displayAwnser01">
      <svg id="bg-anim" width="100%" height="100%" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
        <rect id="a" x="-50" y="70" width="200%" height="0.5" rx="0.5" ry="0.5" viewBox="0 0 100 100" fill="#343a40" >
        </rect>
        <image x="30" y="5" height="40%" width="40%"  xlink:href="../assets/industry.svg" >
          <animateMotion
            path="M 0 0 V 10  Z"
            dur="5s" 
            repeatCount="indefinite" />
        </image>
        <image x="-70" y="62" height="20%" width="20%"  xlink:href="../assets/truck-moving.svg" >
          <animateMotion
            path="M 0 0 H 200"
            dur="4s"
            repeatCount="indefinite" />
        </image>
      </svg>
    </div>
    <div class="question d-flex flex-column align-items-center">
      <h4 class="font-weight-bold" v-if="goodAwnser01">Bravo!</h4>
      <h4 class="font-weight-bold" v-if="badAwnser01">Mauvaise réponse</h4>
      <h5 class="font-weight-bold text-dark" v-if="displayAwnser01">{{ awnser01 }}</h5>  
      <h5 class="m-3" v-if="!displayAwnser01" >{{ question01 }}</h5>
      <h5 class="m-3" v-if="displayAwnser01" >{{ solution01 }}</h5>
      <div>
        <button type="button" class="custom-button btn btn-light m-2" v-bind:class="{ 'd-none' : displayAwnser01}" v-on:click="displayAwnser01 = true" @click="goodAwnser01 = true"> {{ awnserA01 }} </button>
        <button type="button" class="custom-button btn btn-light m-2" v-bind:class="{ 'd-none': displayAwnser01}" v-on:click="displayAwnser01 = true" @click="badAwnser01 = true"> {{ awnserB01 }} </button>
        <a a href="#02" class="js-scrollTo"><button type="button" class="custom-button btn btn-light m-2" v-if="displayAwnser01" >Question suivante</button></a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Question01',
  data() {
    return {
      question01: 'La pollution issue de l’usage d’un téléphone est elle plus importante que celle issue de sa fabrication ?',
      solution01: "L’extraction et le transport des minerais qui composent le téléphone à impact considérable sur l’environnement",
      awnserA01: 'non',
      awnserB01: 'oui',
      awnser01: "La production est plus polluante",
      displayAwnser01: false,
      goodAwnser01: false,
      badAwnser01: false,
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
