<template>
  <div>
    <form>
      <div>
        <label for="name">Name</label>
        <input type="text" id="name" v-model="formValues.name">
      </div>
      <div>
        <label for="profileSummary">Profile Summary</label>
        <textarea id="profileSummary" v-model="formValues.profileSummary"/>
      </div>
      <div>
        <label for="country">Country</label>
        <select name="country" id="country" v-model="formValues.country">
          <option value="usa">USA</option>
          <option value="germany">Germany</option>
          <option value="france">France</option>
        </select>
      </div>

      <div>
        <label for="location">Job Location</label>
        <select name="location" id="location" multiple v-model="formValues.location">
          <option value="usa">USA</option>
          <option value="germany">Germany</option>
          <option value="france">France</option>
        </select>
      </div>
    </form>
    <div>
      <pre>{{JSON.stringify(formValues, null, 2)}}</pre>
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
      formValues: {
        name: '',
        profileSummary: '',
        country: '',
        location: []
      }
    }
  }
}
</script>

<style>

</style>
