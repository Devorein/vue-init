<template>
  <div>
    <p v-if="loading">Loading</p>
    <p v-else-if="error">Error occurred</p>
    <p v-for="(user, index) in users" :key="user">{{index + 1}} {{user}}</p>
    <p v-for="post in posts" :key="post.name">
      Name: {{post.name}}
      <p v-for="likeId in post.likes" :key="likeId">{{likeId}} </p>
    </p>

  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return {
      users: ['user 1', 'user 2'],
      posts: [{
        name: 'post 1',
        published: true,
        likes: [
          1,
          2,
          5,
          8
        ]
      }, {
        name: 'post 2',
        published: false,
        likes: [
          1,
          2,
          5,
          8
        ]
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
