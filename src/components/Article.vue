<template>
  <div>
    <h2 v-bind="$attrs">{{title}}</h2>
    <p>{{likes}}</p>
    <p>{{published ? "Published" : "Private"}}</p>
    <template v-if="loggedInUser.id !== authorId">
      <button @click="$emit('vote', articleId, authorId, amount)">Add Like</button>
      <button @click="$emit('vote', articleId, authorId, -amount)">Remove Like</button>
      <input v-model.number="amount" type="number"/>
    </template>
  </div>
</template>

<script>
  export default {
    name: 'Article',
    props: {
      articleId: {
        type: Number
      },
      title: {
        type: String,
        required: true,
      },
      likes: {
        type: Number,
        default: 0
      },
      authorId: {
        type: Number
      },
      published: Boolean
    },
    inheritAttrs: false,
    inject: ['logged', 'loggedInUser'],
    emits: {
      vote: (authorId, articleId, amount)=>{
        console.log({authorId, articleId, amount})
        return true;
      }
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