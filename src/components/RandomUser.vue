<template>
  <div>
    <h1>{{ name }}</h1>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'randomuser',
  data() {
    return {
      testMessage: 'mic check',
      name: ''
    }
  },
  created() {
    this.getUser()
  },
  methods: {
    getUser() {
      axios.get(`https://randomuser.me/api/`)
        .then(res => {
          this.name = res.data.results[0].name.first
        })
        .catch(e => console.log(e))
    }
  }
}
</script>

<style scoped>

</style>
