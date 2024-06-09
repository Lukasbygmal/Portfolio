<template>
  <MainLayout />
</template>

<script>
import MainLayout from './components/MainLayout.vue'

export default {
  name: 'App',
  components: {
    MainLayout
  }
}
</script>


<style>
html, body {
  margin: 0;
  height: 100%;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #ffffff;
  margin-top: 0;

  background-image: url('./assets/mountain.jpeg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;

  min-height: 100vh;
  width: 100%;
}
</style>
