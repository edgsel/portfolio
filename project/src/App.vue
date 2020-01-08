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
      parallaxStars
    }
  }
</script>

<style>
  #app {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    /*color: #2c3e50;*/
    transition: 0.5s;
  }
</style>
