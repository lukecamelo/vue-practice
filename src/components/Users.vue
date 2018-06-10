<template>

  <div class='users'>

    <h1>{{ testmsg }}</h1>

    <form v-on:submit='addUser'>
      <input type="text" v-model='newUser.name' placeholder='Enter name'><br>
      <input type="text" v-model='newUser.email' placeholder='Enter email'><br>
      <input type="submit" value="submit">
    </form>

    <ul>
      <li v-for='user in users' :key='user.id'>
        <input type="checkbox" class='toggle' v-model='user.contacted'>
        <span :class='{contacted: user.contacted}'>
          {{ user.name }}: {{ user.email }} <button v-on:click='deleteUser(user)'>X</button>
        </span>
      </li>
    </ul>

  </div>

</template>

<script>
export default {
  name: 'users',
  data() {
    return {
      testmsg: 'This is the users component.',
      newUser: {

      },
      users: [
        { id: 0,name: 'Rediscover', contacted: false, email: 'rere@gmail.com' },
        { id: 1,name: 'Ken', contacted: false, email: 'kenk@gmail.com' },
        { id: 2,name: 'Beavis', contacted: false, email: 'ogbobbjohnson@gmail.com' }
      ]
    }
  },
  methods: {
    addUser: function(e) {
      e.preventDefault()
      this.users.push({ name: this.newUser.name, email: this.newUser.email, contacted: false })
    },
    deleteUser: function(user) {
      this.users.splice(this.users.indexOf(user), 1)
    }
  }  
}
</script>

<style scoped>

ul {
  list-style-type: none;
}

.contacted {
  text-decoration: line-through;
}
</style>

