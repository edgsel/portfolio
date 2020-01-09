<template>
  <div id="app">
    <parallaxStars></parallaxStars>
  </div>
</template>

<script>
  import parallaxStars  from './components/parallaxStars';

  export default {
    name: 'app',
    components: {
      parallaxStars,
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
    /*transition: 0.5s;*/
    letter-spacing: 2px;
  }

</style>
