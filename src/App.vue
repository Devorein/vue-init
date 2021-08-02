<template>
  <div>
    <form @submit="submitForm">
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
      <div>
        <input type="checkbox" name="remote" id="remote" v-model="formValues.remote" true-value="Yes" false-value="No">
        <label for="remote">Remote</label>
      </div>
      <div>
        <label>Skill Set</label>
        <input type="checkbox" name="html" value="html" id="html" v-model="formValues.skills">
        <label for="html">HTML</label>
        <input type="checkbox" name="css" value="css" id="css" v-model="formValues.skills">
        <label for="css">CSS</label>
        <input type="checkbox" name="js" value="js" id="js" v-model="formValues.skills">
        <label for="js">JS</label>
      </div>

      <div>
        <label>Years of experience</label>
        <input type="radio" name="0-2" value="0-2" id="0-2" v-model="formValues.experience">
        <label for="0-2">0-2</label>
        <input type="radio" name="3-5" value="3-5" id="3-5" v-model="formValues.experience">
        <label for="3-5">3-5</label>
        <input type="radio" name="6-10" value="6-10" id="6-10" v-model="formValues.experience">
        <label for="6-10">6-10</label>
      </div>

      <div>
        <button type="submit">Submit</button>
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
    submitForm(event){
      event.preventDefault()
      console.log(this.formValues)
    }
  },
  name: 'App',
  data(){
    return {
      formValues: {
        name: '',
        profileSummary: '',
        country: '',
        location: [],
        remote: "Yes",
        skills: [],
        experience: ""
      }
    }
  }
}
</script>

<style>

</style>
