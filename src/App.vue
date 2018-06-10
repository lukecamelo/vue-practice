/* eslint-disable */

<template>
  <div id="app">
    <Weather></Weather>
  </div>
</template>

<script>
import Test from './components/Test'
import Users from './components/Users'
import Weather from './components/Weather'

export default {
  name: 'App',
  components: {
    Test, Users, Weather
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c6aa8;
  margin-top: 60px;
}
</style>
