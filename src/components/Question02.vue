<template>
  <div class="container-fluid d-flex flex-column justify-content-center align-items-center">
    <div class="awnser size-anim d-flex justify-content-center flex-column align-items-center" v-if="displayAwnser02">
      <div class="row">
              <div class="col-3 year-2007">
                <div class="progress progress-bar-vertical m-2" v-if="displayAwnser02">
                  <div class="progress-bar prog-2007" role="progressbar" aria-valuenow="30" aria-valuemin="0" aria-valuemax="100" style="height: 30%;">122
                  </div>
                </div>
                <span class="production-year"><p>2007</p></span>
              </div>
              <div class="col-3 year-2010">
                <div class="progress progress-bar-vertical m-2" v-if="displayAwnser02">
                <div class="progress-bar prog-2010" role="progressbar" aria-valuenow="30" aria-valuemin="0" aria-valuemax="100" style="height: 30%;">305
                  <span class="sr-only">30% Complete</span>
                </div>
                </div>
                  <span class="production-year"><p>2010</p></span>
              </div>
              <div class="col-3 year-2013">
            <div class="progress progress-bar-vertical m-2">
              <div class="progress-bar prog-2013" role="progressbar" aria-valuenow="30" aria-valuemin="0" aria-valuemax="100" style="height: 30%;">1019
                <span class="sr-only">30% Complete</span>
              </div>
          </div>
                <span class="production-year"><p>2013</p></span>
            </div>
        <div class="col-3 year-2016">
        <div class="progress progress-bar-vertical m-2" v-if="displayAwnser02">
          <div class="progress-bar prog-2016" role="progressbar" aria-valuenow="30" aria-valuemin="0" aria-valuemax="100" style="height: 30%;">1470
            <span class="sr-only">30% Complete</span>
          </div>
      </div>
            <span class="production-year"><p>2016</p></span>
        </div>

</div>
<div class="row graph-ligne">
  <p>Production mondiale de téléphones portables exprimée en millions</p>
</div>
    </div>
    <div class="question d-flex flex-column align-items-center">
      <h5 class="font-weight-bold text-dark question-number" v-if="!displayAwnser02">2/5</h5>  
      <h4 class="font-weight-bold" v-if="goodAwnser02">Bravo!</h4>
      <h4 class="font-weight-bold" v-if="badAwnser02">Mauvaise réponse</h4>
      <h5 class="font-weight-bold text-dark" v-if="displayAwnser02">{{ awnser02 }}</h5>  
      <h5 class="m-3" v-if="!displayAwnser02" >{{ question02 }}</h5>
      <h5 class="m-3" v-if="displayAwnser02" >{{ solution02 }}</h5>
      <div>
        <button type="button" class="custom-button btn btn-light m-2" v-bind:class="{ 'd-none' : displayAwnser02}" v-on:click="displayAwnser02 = true" @click="badAwnser02 = true"> {{ awnserA02 }} </button>
        <button type="button" class="custom-button btn btn-light m-2" v-bind:class="{ 'd-none': displayAwnser02}" v-on:click="displayAwnser02 = true" @click="badAwnser02 = true"> {{ awnserB02 }} </button>
        <button type="button" class="custom-button btn btn-light m-2" v-bind:class="{ 'd-none': displayAwnser02}" v-on:click="displayAwnser02 = true" @click="goodAwnser02 = true"> {{ awnserC02 }} </button>
        <a a href="#03" class="js-scrollTo"><img class="arrows mt-3" src="../assets/arrows.svg" v-if="displayAwnser02" ></a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Question02',
  data() {
    return {
      question02: 'Combien de téléphones portables ont été fabriqués depuis 2007 ?',
      solution02: "La variation de la quantité fabriquée chaque année est encore plus alarmante.",
      awnserA02: '700 millions',
      awnserB02: '1 milliard',
      awnserC02: '7 milliards',
      awnser02: "7 milliards de téléphones ont été fabriqués depuis 2007",
      displayAwnser02: false,
      goodAwnser02: false,
      badAwnser02: false,
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
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}


.progress-bar-vertical {
  width: 10vw;
  min-height: 100px;
  display: flex;
  align-items: flex-end;
  float: left;
  background-color:#16b164;
}

 .prog-2007 {
  width: 100%;
  height: 30% !important;
  background-color:rgb(244, 213, 93);
  color:#343a40;
  font-weight: bold;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
  animation: mymove 8s infinite;
  animation-delay: -6s;
}

@keyframes mymove {
  0% {opacity: 0.3;}
  50% {opacity: 1;}
  100% {opacity: 0.3;}
}

.prog-2010 {
  width: 100%;
  height: 50% !important;
  background-color:rgb(247, 177, 57);
  color:#343a40;
  font-weight: bold;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
  animation: mymove 8s infinite;
  animation-delay: -5s;
}

.prog-2013 {
  width: 100%;
  height: 70% !important;
  background-color:rgb(247, 154, 73);
  color:#343a40;
  font-weight: bold;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
  animation: mymove 8s infinite;
  animation-delay: -4s;
}

.prog-2016 {
  width: 100%;
  height: 100% !important;
  background-color:rgb(247, 99, 73);
  color:#343a40;
  font-weight: bold;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
  animation: mymove 8s infinite;
  animation-delay: -3s;
}

.year-2007 {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.year-2010 {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.year-2013 {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.year-2016 {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.graph-ligne {
  display: flex;
  text-align: center !important;
  font-weight: bold;
  font-style: italic;
  margin: 2vh;
}

.numbers {
  max-width: 550px;
  margin:10px;
}


</style>