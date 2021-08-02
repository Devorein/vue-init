<template>
  <div>
    <h2 v-once>{{name}}</h2>
    <button @click="name = 'Arcoden'">Change name</button>
    <h2 v-pre>{{name}}</h2>
  </div>
</template>

<script>

export default {
  methods: {
  },
  name: 'App',
  data(){
    return {
      name: "devorein"
    }
  }
}
</script>

<style>

</style>
