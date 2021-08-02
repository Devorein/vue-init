<template>
  <div>
    <h2>Volume tracker (0-20)</h2>
    <h2>Current volume {{volume}}</h2>
    <div>
      <button @click="volume+=2">+2</button>
      <button @click="volume-=2">-2</button>
    </div>
  </div>
</template>

<script>

export default {
  methods: {},
  name: 'App',
  data(){
    return {
      volume: 0
    }
  },
  computed: {
  },
  watch: {
    volume(newValue, oldValue){
      if(newValue > oldValue && newValue == 16){
        alert("High volume")
      }
    }
  }
}
</script>

<style>

</style>
