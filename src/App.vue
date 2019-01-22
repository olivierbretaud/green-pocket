<template>
  <div id="main-container">
    <start id="00"/>
    <Question01 id="01"/>
    <Question02 id="02"/>
    <Question03 id="03"/>
    <Question04 id="04"/>
    <Question05 id="05"/>
    <End id="06"/>
  </div>
</template>

<script>
import Question05 from './components/Question05.vue'
import Question04 from './components/Question04.vue'
import Question03 from './components/Question03.vue'
import Question02 from './components/Question02.vue'
import Question01 from './components/Question01.vue'
import End from './components/End.vue'
import Start from './components/Start.vue'

export default {
  name: 'app',
  components: {
    Question05,
    Question04,
    Question03,
    Question02,
    Question01,
    Start,
    End
  },
}

$(document).ready(function() {
$('.js-scrollTo').on('click', function() { // Au clic sur un élément
let page = $(this).attr('href'); // Page cible
let speed = 750; // Durée de l'animation (en ms)
$('html, body').animate( { scrollTop: $(page).offset().top }, speed ); // Go
return false;
  }); 
});


</script>

<style>
body {
  font-family: 'Quicksand', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: whitesmoke;
  background-color: #16b164;
}

.custom-button {
color: whitesmoke !important;
border-radius: 20px !important;
border-width: medium !important;
background-color: #16b164;
}

.custom-button:hover {
background-color: whitesmoke !important;
color: #16b164 !important;
border-width: medium !important;
}

.arrows {
  width: 30px !important;
  opacity: 0.7;
}

@media screen and (max-width: 440px) {
   h5 {
    font-size: 1.1em !important;
  }
}

@media screen and (max-width: 374px) {
   h5 {
    font-size: 1em !important;
  }
}

</style>
