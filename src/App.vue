<template>
  <div>
    <p v-if="loading">Loading</p>
    <p v-else-if="error">Error occurred</p>
    <p v-else>{{data.message}}</p>
    <template v-if="display">
      <p>{{data.name}}</p>
      <p>{{data.age}}</p>
    </template>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return {
      data: {
        message: "Hello world",
        name: "devorein",
        age: 20
      },
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
