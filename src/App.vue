<template>
  <div>
    <div>{{count}}</div>
    <input @change="change" type="number"/>
    <button @click="increment($event)">Increase counter</button>
    <button @click="decrement($event)">Decrease counter</button>
  </div>
</template>

<script>

export default {
  methods: {
    increment(){
      this.count+=this.changeBy
    },
    decrement(){
      this.count-=this.changeBy
    },
    change(e){
      this.changeBy = parseInt(e.target.value)
    }
  },
  name: 'App',
  data(){
    return {
      name: "devorein",
      count: 0,
      changeBy: 1
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
