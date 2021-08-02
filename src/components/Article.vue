<template>
  <div>
    <h2 v-bind="$attrs">{{article.title}}</h2>
    <p>{{article.likes}} likes</p>
    <template v-if="loggedInUser.id !== article.authorId">
      <button @click="$emit('vote', article.id, article.authorId, amount)">Add Like</button>
      <button @click="$emit('vote', article.id, article.authorId, -amount)">Remove Like</button>
      <input v-model.number="amount" type="number"/>
    </template>
    <template v-else>
      <Checkbox label="Published"/>
    </template>
  </div>
</template>

<script>
  import Checkbox from "./Checkbox.vue";
  export default {
    name: 'Article',
    props: ['article'],
    inheritAttrs: false,
    inject: ['logged', 'loggedInUser'],
    emits: {
      vote: (authorId, articleId, amount)=>{
        console.log({authorId, articleId, amount})
        return true;
      }
    },
    components: {
      Checkbox
    },
    data(){
      return {
        amount: 1
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>