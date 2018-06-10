/* eslint-disable */

<template>
  <div>
    <h1>Name: {{ fullName }}</h1>
    <h2>Address: {{ street }}, {{ city }} {{ state }} </h2>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'randomuser',
  data() {
    return {
      testMessage: 'mic check',
      firstName: '',
      lastName: '',
      street: '',
      city: '',
      state: ''
    }
  },
  props: {
    testProp: {
      type: String,
      default: '1 2 1 2 1 2'
    }
  },
  created() {
    this.getUser()
  },
  methods: {
    getUser() {
      axios.get(`https://randomuser.me/api/`)
        .then(res => {
          let data = res.data.results[0]

          this.firstName = data.name.first
          this.lastName = data.name.last
          this.street = data.location.street
          this.state = data.location.state
          this.city = data.location.city
        })
        .catch(e => console.log(e))
    }
  },
  computed: {
    fullName: function() {
      return this.firstName + ' ' + this.lastName
    }
  }
}
</script>

<style scoped>
  * {
    color: black;
  }
</style>
