<template>
  <div id="main-container">
    <!-- <Question01 /> -->
    <Question02 />
  </div>
</template>

<script>
// import Question01 from './components/Question01.vue'
import Question02 from './components/Question02.vue'

export default {
  name: 'app',
  components: {
    // Question01,
    Question02
  }
}
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
</style>
