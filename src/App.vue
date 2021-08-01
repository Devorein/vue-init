<template>
  <div>
    <div v-for="post in fetchPosts()" :key="post.name">
      {{post.name}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  methods: {
    sum(a, b, c){
      return a + b + c
    },
    fetchPosts(){
      return this.posts
    }
  },
  data(){
    return {
      users: ['user 1', 'user 2'],
      posts: [{
        name: 'post 1',
        published: true,
      }, {
        name: 'post 2',
        published: false,
      }],
      display: false,
      loading: false,
      error: false
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.danger{
  color: red;
}

.safe{
  color: green;
}

.bold{
  font-weight: bolder;
}
</style>
