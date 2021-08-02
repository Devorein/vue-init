<template>
  <div>
    <div v-for="user in users" :key="'user.'+user.id">
      <Greet :username="user.username" :fullname="user.fullname"/>
      <div v-for="article in user.articles" :key="'article.'+article.id">
        <Article :authorId="article.authorId" :title="article.title" :likes="article.likes" :published="article.published"/>
      </div>
    </div>
  </div>
</template>

<script>
import Greet from "./components/Greet.vue"
import Article from "./components/Article.vue"

const users = [{
  id: 1,
  username: "Devorein",
  fullname: "Devon Reid",
  articles: [
    {
      title: "Article 1",
      published: false,
      likes: 0,
      id: 1,
      authorId: 1
    },
    {
      title: "Article 2",
      published: true,
      likes: 10,
      id: 2,
      authorId: 1
    }
  ]
}, {
  id: 2,
  username: "Arcoden",
  fullname: "Arden Claise",
  articles: [
    {
      title: "Article 3",
      published: true,
      likes: 0,
      id: 3,
      authorId: 2
    },
    {
      title: "Article 4",
      published: true,
      likes: 32,
      id: 4,
      authorId: 2
    }
  ]
}];

export default {
  components: {
    Greet,
    Article
  },
  name: 'App',
  data(){
    return {
      users
    }
  },
  provide() {
    return {
      logged: true,
      loggedInUser: users.find(user => user.id === 1)
    }
  }
}
</script>

<style>

</style>
