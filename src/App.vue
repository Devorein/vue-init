<template>
  <div>{{greet}} {{name}}</div>
  <div v-text="text"></div>
  <div v-html="html"></div>
  <p v-bind:class="isDanger ? 'danger bold' : 'safe bold'" >Heading</p>
  <button v-bind:disabled="isDisabled">Disable</button>
  <p v-bind:class="{
    danger: isDanger,
    safe: !isDanger,
    bold: true
  }">Hello World</p>
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
      isDisabled: true,
      isDanger: true
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
