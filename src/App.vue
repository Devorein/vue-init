<template>
  <div>{{greet}} {{name}}</div>
  <div v-text="text"></div>
  <div v-html="html"></div>
  <h2 id="headingId">Heading</h2>
  <button v-bind:disabled="isDisabled">Disable</button>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      text: "Hello World",
      greet: "Hello",
      name: "devorein",
      html: "<b>Strong text</b>",
      headingId: 'heading',
      isDisabled: true
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
</style>
