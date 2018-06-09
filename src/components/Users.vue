<template>
  <div class='users'>
    <h1>{{ testmsg }}</h1>

    <ul>
      <li v-for='user in users' :key='user.id'>
        {{ user.name }}: {{ user.email }}
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
      users: [
        { id: 0,name: 'Rediscover', contacted: false, email: 'rere@gmail.com' },
        { id: 1,name: 'Ken', contacted: false, email: 'kenk@gmail.com' },
        { id: 2,name: 'Beavis', contacted: false, email: 'ogbobbjohnson@gmail.com' }
      ]
    }
  },
  methods: {

  }  
}
</script>

<style scoped>

ul {
  list-style-type: none;
}

</style>

