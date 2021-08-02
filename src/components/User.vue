<template>
  <div>
    <div>
      Fullname: {{user.fullname}}
    </div>
    <div>
      Username: {{user.username}}
    </div>
    <div v-for="article in user.articles" :key="'article.'+article.id">
      <Article :authorId="article.authorId" :title="article.title" :likes="article.likes" :published="article.published" :articleId="article.id" @vote="vote"/>
    </div>
  </div>
</template>

<script>
  import Article from "./Article.vue"
  export default {
    components: {
      Article
    },
    name: "User",
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