/* eslint-disable */

<template>
  <div id="app">
    <RandomUser></RandomUser>
  </div>
</template>

<script>
import Test from './components/Test'
import Users from './components/Users'
import RandomUser from './components/RandomUser'

export default {
  name: 'App',
  components: {
    Test, Users, RandomUser
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
