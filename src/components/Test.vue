<template>

  <div class='test'>

    <h1>{{ title }}</h1>

    <p v-text="user.firstName"></p>

    <p v-if="showName" v-text="user.lastName"></p>
    
    <ul>
      <li v-for="item in items" :key='item.id'>
        {{ item.title }} {{ item.id }}
      </li>
    </ul>

  </div>

</template>

<script>
export default {
  name: 'test',
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
  }
}
</script>

<style scoped>

</style>

