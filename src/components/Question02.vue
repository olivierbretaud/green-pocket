<template>
  <div class="container-fluid d-flex flex-column justify-content-center align-items-center">
    <div class="awnser size-anim d-flex justify-content-center flex-column align-items-center" v-if="displayAwnser">
      <div class="row numbers">
        <div class="col-3 col-lg-3 col-md-3 col-sm-3 year-2007 ">
          <div class="progress progress-bar-vertical mr-0 mb-2">
            <div class="progress-bar prog-2007" role="progressbar" aria-valuenow="30" aria-valuemin="0" aria-valuemax="100" style="height: 30%;">122
              <span class="sr-only">30% Complete</span>
            </div>
          </div>
          <span class="production-year"><p>2007</p></span>
        </div>
        <div class="col-3 col-lg-3 col-md-3 col-sm-3 year-2010">
          <div class="progress progress-bar-vertical mr-0 mb-2">
          <div class="progress-bar prog-2010" role="progressbar" aria-valuenow="30" aria-valuemin="0" aria-valuemax="100" style="height: 30%;">305
            <span class="sr-only">30% Complete</span>
          </div>
          </div>
            <span class="production-year"><p>2010</p></span>
        </div>
        <div class="col-3 col-lg-3 col-md-3 col-sm-3 year-2013">
      <div class="progress progress-bar-vertical mr-0 mb-2">
        <div class="progress-bar prog-2013" role="progressbar" aria-valuenow="30" aria-valuemin="0" aria-valuemax="100" style="height: 30%;">1019
          <span class="sr-only">30% Complete</span>
        </div>
    </div>
          <span class="production-year"><p>2013</p></span>
      </div>
   <div class="col-3 col-lg-3 col-md-3 col-sm-3 year-2016">
   <div class="progress progress-bar-vertical mr-0 mb-2">
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
      <h4 class="font-weight-bold" v-if="goodAwnser">Bravo!</h4>
      <h4 class="font-weight-bold" v-if="badAwnser">Mauvaise réponse</h4>
      <h5 class="m-3" v-if="!displayAwnser" >{{ question }}</h5>
      <h5 class="m-3" v-if="displayAwnser" >{{ solution }}</h5>
      <div>
        <button type="button" class="custom-question btn btn-light m-2" v-bind:class="{ 'd-none' : displayAwnser}" v-on:click="displayAwnser = true" @click="badAwnser = true"> {{ awnserA }} </button>
        <button type="button" class="custom-question btn btn-light m-2" v-bind:class="{ 'd-none': displayAwnser}" v-on:click="displayAwnser = true" @click="badAwnser = true"> {{ awnserB }} </button>
        <button type="button" class="custom-question btn btn-light m-2" v-bind:class="{ 'd-none': displayAwnser}" v-on:click="displayAwnser = true" @click="goodAwnser = true"> {{ awnserC }} </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Question02',
  data() {
    return {
      question: 'Sais-tu combien de téléphones portables ont été fabriqué depuis 2007 ?',
      solution: "Environ 7 milliards de téléphones ont été fabriqué depuis 2007. La progression de la quantité fabriquée chaque année est encore plus impresionnante.",
      awnserA: '700 millions',
      awnserB: '1 milliard',
      awnserC: '7 milliards',
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

.custom-question {
color: whitesmoke !important;
border-radius: 20px !important;
border-width: medium !important;
background-color: #16b164;
}

.custom-question:hover {
background-color: whitesmoke !important;
color: #16b164 !important;
border-width: medium !important;
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
  -webkit-transition: height 0.6s ease;
  -o-transition: height 0.6s ease;
  transition: height 0.6s ease;
  background-color:rgb(244, 213, 93);
  color: black;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
}

.prog-2010 {
  width: 100%;
  height: 50% !important;
  -webkit-transition: height 0.6s ease;
  -o-transition: height 0.6s ease;
  transition: height 0.6s ease;
  background-color:rgb(247, 177, 57);
  color: whitesmoke;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
}

.prog-2013 {
  width: 100%;
  height: 70% !important;
  -webkit-transition: height 0.6s ease;
  -o-transition: height 0.6s ease;
  transition: height 0.6s ease;
  background-color:rgb(247, 154, 73);
  color: whitesmoke;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
}

.prog-2016 {
  width: 100%;
  height: 100% !important;
  -webkit-transition: height 0.6s ease;
  -o-transition: height 0.6s ease;
  transition: height 0.6s ease;
  background-color:rgb(247, 99, 73);
  color: whitesmoke;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
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

@keyframes prog-2016 {
  from {
    height: 0vh;
    opacity: 0;
  }
  to {
    height: 100%;
    opacity: 1;
  }
}

</style>