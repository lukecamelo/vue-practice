<template>
  <div>
    <h1>{{ location }}</h1>
    <h2>{{ temp }}</h2>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'weather',
  data() {
    return {
      testMessage: 'mic check',
      lat: null,
      lon: null,
      location: null,
      apiKey: 'b7ed1afa86c47e8f23a654b41b195fc5',
      temp: null
    }
  },
  created() {
    navigator.geolocation.getCurrentPosition(pos => {
      console.log('get coords', pos.coords)
      this.lat = pos.coords.latitude
      this.lon = pos.coords.longitude
      this.loadWeather()
    })
  },
  methods: {
    loadWeather() {
      axios.get(`http://api.openweathermap.org/data/2.5/weather?q=London&APPID=b7ed1afa86c47e8f23a654b41b195fc5`)
        .then(res => {
          let weather = res.main

          this.temp = res.main.temp
          this.location = res.name
        })
        .catch(e => console.log(e))
    }
  }
}
</script>

<style scoped>

</style>
