<template>
  <div>
    <div v-for="item in filteredItems" :key="item.name">
      <h2>{{item.name}}</h2>
      <h2>{{item.age}}</h2>
    </div>
  </div>
</template>

<script>

export default {
  methods: {

  },
  name: 'App',
  data(){
    return {
      items: [{
        name:"devorein",
        age: 20
      }, {
        name: "arcoden",
        age: 21
      }],
    }
  },
  computed: {
    filteredItems(){
      return this.items.filter(item=>item.age <= 20)
    }
  }
}
</script>

<style>

</style>
