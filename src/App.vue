<template>
  <div>
    <h2>Firstname {{firstname}}</h2>
    <h2>Lastname {{lastname}}</h2>
    <h2>Computed fullname {{fullname}}</h2>
    <h2>{{ages.reduce((cur, next)=>cur+next, 0)}}</h2>
    <h2>Computed age {{computedAge}}</h2>
    <h2>Calculated age {{getTotalAge()}}</h2>
    <button @click="ages.push(25)">Add item</button>
    <button @click="firstname='firstname'">Change firstname</button>
  </div>
</template>

<script>

export default {
  methods: {
    getTotalAge(){
      console.log("method")
      return this.ages.reduce((cur, next)=>cur+next, 0)
    }
  },
  name: 'App',
  data(){
    return {
      ages: [20, 31, 44, 13],
      firstname: "Safwan",
      lastname: "Shaheer"
    }
  },
  computed: {
    computedAge(){
      console.log("computed")
      return this.ages.reduce((cur, next)=>cur+next, 0)
    },
    fullname(){
      return `${this.firstname} ${this.lastname}`
    }
  }
}
</script>

<style>

</style>
