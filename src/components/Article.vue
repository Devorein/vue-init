<template>
  <div>
    <Card>
      <template v-slot:header>
        <h2 v-bind="$attrs">{{article.title}}</h2>
      </template>
      <template v-slot:content>
        <p>{{article.likes}} likes</p>
        <p>{{ article.published ? "Published" : "Private"}}</p>
        <template v-if="loggedInUser.id !== article.authorId">
          <button @click="$emit('vote', article.id, article.authorId, amount)">Add Like</button>
          <button @click="$emit('vote', article.id, article.authorId, -amount)">Remove Like</button>
          <input v-model.number="amount" type="number"/>
        </template>
        <template v-else>
          <Checkbox :checked="article.published" label="Published" @click="publish"/>
        </template>
      </template>
      <template v-slot:footer>
        <button>View details</button>
      </template>
    </Card>
  </div>
</template>

<script>
  import Checkbox from "./Checkbox.vue";
  import Card from "./Card.vue";
  export default {
    name: 'Article',
    props: ['article'],
    inheritAttrs: false,
    inject: ['logged', 'loggedInUser', 'users'],
    components: {
      Checkbox,
      Card
    },
    data(){
      return {
        amount: 1
      }
    },
    methods: {
      publish(){
        if(this.article.authorId === this.loggedInUser.id){
          const article = this.loggedInUser.articles.find(article=>article.id === this.article.id);
          if(article){
            article.published = !article.published
          }
        }
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>