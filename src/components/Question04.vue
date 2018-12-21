<template>
  <div class="container-fluid d-flex flex-column justify-content-center align-items-center">
    <div class="awnser size-anim d-flex justify-content-center flex-column align-items-center" v-if="displayAwnser04">
      <div class="donut">
         <div class="donut-chart-block block">
           <h6 class="chart-title mb-3">Emission de gaz à effet de serre d'un téléphone portable</h6>
              <div class="donut-chart">
                <div id="segment1" class="recorte">
                  <div class="quesito " data-rel="80">
                  </div>
                </div>
                <div id="segment2" class="recorte">
                  <div class="quesito transport" data-rel="16">
                  </div>
                </div>
                <div id="segment3" class="recorte">
                  <div class="quesito usage" data-rel="3">
                  </div>
                </div>
                <div id="segment4" class="recorte">
                  <div class="quesito production" data-rel="1">
                  </div>
                </div>
                <p class="center-date"><br><span class="scnd-font-color"></span></p>
              </div>
              <ul class="os-percentages horizontal-list">
                <li>
                  <p class="production-scnd-font-color">Production</p>
                  <p class="gas-percentage">80<sup>%</sup></p>
                </li>
                <li>
                  <p class="usage-scnd-font-color">Usage</p>
                  <p class="gas-percentage">16<sup>%</sup></p>
                </li>
                <li>
                  <p class="transport-scnd-font-color">Transport</p>
                  <p class="gas-percentage">3<sup>%</sup></p>
                </li>
                <li>
                  <p class="recycling-scnd-font-color">Recyclage</p>
                  <p class="gas-percentage">1<sup>%</sup></p>
                </li>
              </ul>
            </div>
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
      question04: "Quelle est la princiaple source d'émission à effet de serre des téléphones ?",
      solution04: "La part des technologies de l’information pourrait atteindre 14 % du total des émissions de gaz à effet de serre d’ici 2040, soit plus de la moitié des émissions causées par l’industrie du transport",
      awnserA04: 'Le transport',
      awnserB04: "L'usage",
      awnserC04: "La production",
      awnser04: "La production répresente la principale source d'émission.",
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

.donut-chart {
  position: relative;
	width: 200px;
  height: 200px;
	margin: 0 auto 2rem;
	border-radius: 100%
 }
p.center-date {
  background: #16b164;
  position: absolute;
  text-align: center;
	font-size: 28px;
  top:0;left:0;bottom:0;right:0;
  width: 130px;
  height: 130px;
  margin: auto;
  border-radius: 50%;
  line-height: 35px;
  padding: 15% 0 0;
}
.center-date span.scnd-font-color {
 line-height: 0; 
}
.recorte {
    border-radius: 40%;
    clip: rect(0px, 200px, 200px, 100px);
    height: 100%;
    position: absolute;
    width: 100%;
  }
.quesito {
    border-radius: 50%;
    clip: rect(0px, 100px, 200px, 0px);
    height: 100%;
    position: absolute;
    width: 100%;
    font-family: monospace;
    font-size: 1.5rem;
  }
#segment1 {
    transform: rotate(0deg);
  }

#segment1 .quesito {
    background-color: rgb(250, 209, 72);
    transform: rotate(3.6deg);
  }
#segment2 {
    transform: rotate(3.7deg);
  }
#segment2 .quesito {
    background-color: rgb(247, 181, 82);
    transform: rotate(14.4deg);
  }
#segment3 {
    transform: rotate(14.5deg);
  }
#segment3 .quesito {
    background-color: rgb(245, 142, 78);
    transform: rotate(68.4deg);
  }
#segment4 {
    transform:rotate(68.5deg);
  }
#segment4 .quesito {
    background-color: rgb(187, 103, 88);
    transform: rotate(200deg);
  }

  .production-scnd-font-color {
    color:rgb(187, 103, 88);
    font-weight: bold;
    font-size: 0.8em;
  }
    .usage-scnd-font-color {
    color:rgb(245, 142, 78);
    font-weight: bold;
    font-size: 0.8em;
  }
    .transport-scnd-font-color {
    color:rgb(247, 181, 82);
    font-weight: bold;
    font-size: 0.8em;
  }
      .recycling-scnd-font-color {
    color:rgb(250, 209, 72);
    font-weight: bold;
    font-size: 0.8em;
  }
</style>