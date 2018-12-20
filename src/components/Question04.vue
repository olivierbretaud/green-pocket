<template>
  <div class="container-fluid d-flex flex-column justify-content-center align-items-center">
    <div class="awnser size-anim d-flex justify-content-center flex-column align-items-center" v-if="displayAwnser04">
      <div class="container">

</div>
    </div>
      <div class="question d-flex flex-column align-items-center">
        <h5 class="font-weight-bold text-dark question-number" v-if="!displayAwnser04">4/5</h5>  
        <h4 class="font-weight-bold" v-if="goodAwnser04">Bravo!</h4>
        <h4 class="font-weight-bold" v-if="badAwnser04">Mauvaise réponse</h4>
        <h5 class="font-weight-bold text-dark" v-if="displayAwnser04">{{ awnser04 }}</h5>  
        <h5 class="m-3" v-if="!displayAwnser04" >{{ question04 }}</h5>
        <h5 class="m-3" v-if="displayAwnser04" >{{ solution04 }}</h5>
        <div>
        <button type="button" class="custom-button btn btn-light m-2" v-bind:class="{ 'd-none' : displayAwnser04}" v-on:click="displayAwnser04 = true" @click="badAwnser04 = true"> {{ awnserA04 }} </button>
        <button type="button" class="custom-button btn btn-light m-2" v-bind:class="{ 'd-none': displayAwnser04}" v-on:click="displayAwnser04 = true" @click="badAwnser04 = true"> {{ awnserB04 }} </button>
        <button type="button" class="custom-button btn btn-light m-2" v-bind:class="{ 'd-none': displayAwnser04}" v-on:click="displayAwnser04 = true" @click="goodAwnser04 = true"> {{ awnserC04 }} </button>
        <a a href="#05" class="js-scrollTo"><img class="arrows mt-3" src="../assets/arrows.svg" v-if="displayAwnser04" ></a>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Question04',
  data() {
    return {
      question04: "Combien d'eau a été besoin pour aller aux toilettes ?",
      solution04: "La progression de la quantité fabriquée chaque année est encore plus alarmante.",
      awnserA04: '700 millions',
      awnserB04: '1 milliard',
      awnserC04: '7 milliards',
      awnser04: "7 milliards de téléphones ont été fabriqué depuis 2007",
      displayAwnser04: false,
      goodAwnser04: false,
      badAwnser04: false,
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
    width: 96vw;
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
    width: 96vw;
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