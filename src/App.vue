<template>
  <div>
    <input type="text" v-model="movie"/>
    <input type="text" v-model="user.name"/>
    <input type="number" v-model.number="user.age"/>
    <div v-for="(username, index) in usernames" :key="username">
      <input type="text" @change="onChange(usernames, index, $event)"/>
    </div>
  </div>
</template>

<script>

export default {
  methods: {
    onChange(usernames, index, event){
      usernames[index] = event.target.value
    }
  },
  name: 'App',
  data(){
    return {
      movie: '',
      user: {
        name: "Safwan Shaheer",
        age: 20
      },
      usernames: ["devorein", "arcoden"]
    }
  },
  computed: {
  },
  watch: {
    movie: {
      handler(newValue){
        console.log(`Calling api with the movie name ${newValue}`)
      },
      immediate: true
    },
    user: {
      handler(newValue){
        console.log(`Calling api for the user with name ${newValue.name} and age ${newValue.age}`)
      },
      deep: true,
      immediate: true
    },
    usernames: {
      handler(newValue){
        console.log(`Calling api for the user with new usernames ${newValue}`)
      },
      deep: true,
      immediate: true
    }
  }
}
</script>

<style>

</style>
