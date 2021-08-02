<template>
  <div>
    <div v-for="user in users" :key="user.username">
      <Greet :username="user.username" :fullname="user.fullname"/>
    </div>
    <Article title="Article Title" :isPublished="true"/>
  </div>
</template>

<script>
import Greet from "./components/Greet.vue"
import Article from "./components/Article.vue"

export default {
  components: {
    Greet,
    Article
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
