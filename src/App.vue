<template>
  <div>
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
    <p v-bind:style="{
      color: isDanger ? 'red' : 'green',
      fontWeight: isDanger ? 'normal' : 'bold',
      margin: '50px'
    }">Dynamic style using object</p>
    <p v-bind:style="style">Dynamic style using variable</p>
    <p v-bind:style="[style, style2]">Dynamic style using array of variables</p>
    <p v-bind:style="[{
      color: isDanger ? 'red' : 'green',
      fontWeight: isDanger ? 'normal' : 'bold',
      margin: '50px'
    }, {
      backgroundColor: 'red',
      textDecoration: 'underline',
      color: 'yellow'
    }]">Dynamic style using array of style objects</p>
  </div>
</template>

<script>
const isDanger = true;
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
      isDanger,
      style: {
        color: isDanger ? 'red' : 'green',
        fontWeight: isDanger ? 'normal' : 'bold',
        margin: '50px'
      },
      style2: {
        backgroundColor: "red",
        textDecoration: 'underline',
        color: 'white'
      }
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
