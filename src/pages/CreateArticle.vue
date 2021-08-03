<template>
  <div>
    <input v-model="title" />
    <Checkbox :checked="published" label="Published" @click="published = !published"/>
    <button @click="createArticle">Create Article</button>
  </div>
</template>

<script>
  import Checkbox from "../components/base/Checkbox.vue";

  export default {
    name: 'CreateArticle',
    components: {
      Checkbox
    },
    inject: ['loggedInUser'],
    data(){
      return {
        title: '',
        published: false
      }
    },
    methods: {
      createArticle(){
        this.loggedInUser.articles.push({
          title: this.title,
          published: this.published,
          likes: 0,
          id: this.loggedInUser.articles.length + 1,
          authorId: this.loggedInUser.id
        })
        this.title = ''
        this.published = false
      }
    }
  }
</script>

<style scoped>

</style>