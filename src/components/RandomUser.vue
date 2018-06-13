/* eslint-disable */

<template>
  <div>
    <h1>Name: {{ fullName }}</h1>
    <h2>Address: {{ street }}, {{ city }} {{ state }} </h2>
    <h3>This dumbass has their password available for everyone to see here look: {{ password }}</h3>
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
      state: '',
      password: ''
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
          this.password = data.login.password
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
    text-align: center;
  }

</style>
