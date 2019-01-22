<template>
  <div class="container-fluid d-flex flex-column justify-content-center align-items-center">
    <div class="awnser size-anim d-flex justify-content-center flex-column align-items-center" v-if="displayAwnser04">
      <div class="donut">
            <svg width="80%" height="80%" viewBox="0 0 42 42" class="donut">
              <circle class="donut-hole" cx="21" cy="21" r="15.91549430918954" fill="#16b164"></circle>
              <circle class="donut-ring" cx="21" cy="21" r="15.91549430918954" fill="transparent" stroke="#d2d3d4" stroke-width="3"></circle>
              <circle class="donut-segment" cx="21" cy="21" r="15.91549430918954" fill="transparent" stroke="#343a40" stroke-width="3" stroke-dasharray="80 20" stroke-dashoffset="25"></circle>        
              <text x="26%" y="65%" fill="#343a40" font-size="4">Production</text>
              <text x="24%" y="53%" fill="#343a40" font-size="10"> 80 % </text>
            </svg>
          <ul class="horizontal-list">
            <li>
              <p class="percentage">Usage: 6%</p>
            </li>
            <li>
              <p class="percentage">Transport: 3%</p>
            </li>
            <li>
              <p class="percentage">Recyclage: 1%</p>
            </li>
          </ul>
      </div>
    </div>
      <div class="question d-flex flex-column align-items-center">
        <h5 class="font-weight-bold text-dark question-number" v-if="!displayAwnser04">4/5</h5>  
        <h4 class="font-weight-bold mt-4" v-if="goodAwnser04">Bravo!</h4>
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
      question04: "Quelle est la princiaple source d'émission à effet de serre des téléphones ?",
      solution04: "La part des technologies de l’information pourrait atteindre 14 % du total des émissions de gaz à effet de serre d’ici 2040.",
      awnserA04: 'Le transport',
      awnserB04: "L'usage",
      awnserC04: "La production",
      awnser04: "La production répresente la principale source d'émission.",
      displayAwnser04: false,
      goodAwnser04: false,
      badAwnser04: false,
    }
  },
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
  margin: 20px;
}

.awnser {
  width: 96vw;
  height: 40vh;
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
    height: 40vh;
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
    height: 40vh;
    opacity: 1;
  }
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  font-size: 1.2em;
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

.percentage {
  color: #343a40;
  font-weight: bold;
}

.horizontal-list {
  display: block;
}

@media screen and (max-width: 640px) {
  .horizontal-list {
    display: none;
  }
}

</style>