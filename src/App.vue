<template>
  <div>
    <div v-for="user in users" :key="user.username">
      <Greet :username="user.username" :fullname="user.fullname"/>
    </div>
  </div>
</template>

<script>
import Greet from "./components/Greet.vue"

export default {
  components: {
    Greet
  },
  name: 'App',
  data(){
    return {
      users: [{
        username: "Devorein",
        fullname: "Devon Reid"
      }, {
        username: "Arcoden",
        fullname: "Arden Claise"
      }]
    }
  }
}
</script>

<style>

</style>
