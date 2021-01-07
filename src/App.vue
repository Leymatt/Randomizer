<template>
  <div id="app">
    <RandomBox />
  </div>
</template>

<script>
import RandomBox from './components/RandomBox.vue'

export default {
  name: 'App',
  components: {
    RandomBox
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Oswald:wght@300;400;500;600;700&display=swap');

#app {
  font-family: 'Oswald', sans-serif;;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

* {
  margin: 0;
  outline: none;
  border: none;
  padding: 0;
}

body {
  margin: 0;
}
</style>
