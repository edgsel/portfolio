<template>
  <div id="app">
    <app-header></app-header>
    <router-view></router-view>
  </div>
</template>

<script>
  import parallaxStars  from './components/parallaxStars';
  import app_header from "./components/header";

  export default {
    name: 'app',
    components: {
      'app-header': app_header
    },

    data() {
      return {
        parallaxStars
      }
    }

  }

</script>

<style>

  @import url('https://fonts.googleapis.com/css?family=Julius+Sans+One&display=swap');

  #app {
    font-size: 1.6rem;
    font-family: 'Julius Sans One', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #ffffff;
    letter-spacing: 2px;
  }

</style>
