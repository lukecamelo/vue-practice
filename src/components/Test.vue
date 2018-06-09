/* eslint-disable */

<template>

  <div class='test'>

    <input type="text" v-model="title">
    <h1>{{ title }}</h1>

    <p v-text="user.firstName"></p>

    <p v-if="showName" v-text="user.lastName"></p>

    <ul>
      <li v-for="item in items" :key='item.id'>
        {{ item.title }} {{ item.id }}
      </li>
    </ul>

    <button v-on:click="nameChange">Luke -> Billy -> Luke</button>
    <input type="text" v-on:keyup='pressKey' v-on:keyup.enter='weewoo'>
    <hr>
    <label>first name</label>
    <input type="text" v-model='user.firstName'>
    <br>
    <label>last name</label>
    <input type="text" v-model='user.lastName'>
    <br>
    <h3>{{ fullName }}</h3><br>
    <h2>{{ msg }}</h2>
  </div>

</template>

<script>
export default {
  name: 'test',
  props: {
    msg: {
      type: String,
      default: 'Foobar'
    }
  },
  data() {
    return {
      title: 'Hello world!',
      user: {
        firstName: 'Luke',
        lastName: 'Camelo'
      },
      showName: true,
      items: [
        { title: 'boop', id: 1 },
        { title: 'blip', id: 2 },
        { title: 'bebebe', id: 3 }
      ]
    }
  },
  methods: {
    nameChange: function() {
      if(this.user.firstName === 'Luke') {
        this.user.firstName = 'Billy'
      } else {
        this.user.firstName = 'Luke'
      }
    },
    pressKey: function(e) {
      console.log(e.target.value)
    },
    weewoo: function() {
      alert('wee woo')
    }
  },
  computed: {
    fullName: function() {
      return this.user.firstName + ' ' + this.user.lastName
    }
  }
}
</script>

<style scoped>

</style>

