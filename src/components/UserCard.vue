<template>
  <div>
    <div>
      Fullname: {{user.fullname}}
    </div>
    <div>
      Username: {{user.username}}
    </div>
    <div v-for="article in user.articles" :key="'article.'+article.id">
      <ArticleCard :article="article" @vote="vote"/>
    </div>
  </div>
</template>

<script>
  import ArticleCard from "./ArticleCard.vue"
  export default {
    components: {
      ArticleCard
    },
    name: "UserCard",
    props: [
      'user',
    ],
    inject: ['users'],
    methods: {
      vote(articleId, userId, amount){
        const user = this.users.find(user=>user.id === userId);
        if(user){
          const article = user.articles.find(article=>article.id === articleId);
          if(article){
            article.likes += amount
          }
        }
      }
    },
  }
</script>

<style scoped>

</style>