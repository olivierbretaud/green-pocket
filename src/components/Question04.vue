<template>
  <div class="container-fluid d-flex flex-column justify-content-center align-items-center">
    <div class="awnser size-anim d-flex justify-content-center flex-column align-items-center" v-if="displayAwnser04">
      <div class="donut">
         <div class="donut-chart-block block">
           <h2 class="titular">OS AUDIENCE STATS</h2>
              <div class="donut-chart">
                <div id="porcion1" class="recorte">
                  <div class="quesito ios" data-rel="21">
                  </div>
                </div>
                <div id="porcion2" class="recorte"><div class="quesito mac" data-rel="39"></div></div>
                <div id="porcion3" class="recorte"><div class="quesito win" data-rel="31"></div></div>
                <div id="porcionFin" class="recorte"><div class="quesito linux" data-rel="9"></div></div>
                <p class="center-date">JUNE<br><span class="scnd-font-color">2013</span></p>        
              </div>
              <ul class="os-percentages horizontal-list">
                  <li>
                      <p class="ios os scnd-font-color">iOS</p>
                      <p class="os-percentage">21<sup>%</sup></p>
                  </li>
                  <li>
                      <p class="mac os scnd-font-color">Mac</p>
                      <p class="os-percentage">39<sup>%</sup></p>
                  </li>
                  <li>
                      <p class="linux os scnd-font-color">Linux</p>
                      <p class="os-percentage">9<sup>%</sup></p>
                  </li>
                  <li>
                      <p class="win os scnd-font-color">Win</p>
                      <p class="os-percentage">31<sup>%</sup></p>
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

.donut-chart {
  position: relative;
	width: 200px;
  height: 200px;
	margin: 0 auto 2rem;
	border-radius: 100%
 }
p.center-date {
  background: #394264;
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
    border-radius: 50%;
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
#porcion1 {
    transform: rotate(0deg);
  }

#porcion1 .quesito {
    background-color: #E64C65;
    transform: rotate(76deg);
  }
#porcion2 {
    transform: rotate(76deg);
  }
#porcion2 .quesito {
    background-color: #11A8AB;
    transform: rotate(140deg);
  }
#porcion3 {
    transform: rotate(215deg);
  }
#porcion3 .quesito {
    background-color: #4FC4F6;
    transform: rotate(113deg);
  }
#porcionFin {
    transform:rotate(-32deg);
  }
#porcionFin .quesito {
    background-color: #FCB150;
    transform: rotate(32deg);
  }
.nota-final {
  clear: both;
  color: #4FC4F6;
  font-size: 1rem;
  padding: 2rem 0;
}
.nota-final strong {
  color: #E64C65;
}
.nota-final a {
  color: #FCB150;
  font-size: inherit;
}

</style>