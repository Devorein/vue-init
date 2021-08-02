<template>
  <div>
    <div>
      Fullname {{fullname}}
    </div>
    <button @click="changeFullname">Change fullname</button>
  </div>
</template>

<script>

export default {
  methods: {
    changeFullname(){
      this.fullname = "Arden Claise"
    }
  },
  name: 'App',
  data(){
    return {
      firstname: "Safwan",
      lastname: "Shaheer",
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
    fullname: {
      get(){
        return `${this.firstname} ${this.lastname}`
      },
      set(value){
        const [firstname, lastname] = value.split(" ")
        this.firstname = firstname
        this.lastname = lastname
      }
    },
    filteredItems(){
      return this.items.filter(item=>item.age <= 20)
    }
  }
}
</script>

<style>

</style>
