<template>
  <div>
    <Tabs @click="onTabChange" :tabs="['Users', 'CreateArticle']"/>

    <component :is="activeTab"/>
  </div>
</template>

<script>
import Users from "./pages/Users.vue"
import Tabs from "./components/base/Tabs.vue"
import CreateArticle from "./pages/CreateArticle.vue";

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
    Users,
    Tabs,
    CreateArticle
  },
  name: 'App',
  data(){
    return {
      users,
      activeTab: 'Users'
    }
  },
  methods: {
    onTabChange(tab){
      this.activeTab = tab
    }
  },
  provide() {
    return {
      logged: true,
      loggedInUser: users.find(user => user.id === 1),
      users: this.users
    }
  }
}
</script>

<style>
body{
  font-family: "Arial";
}
</style>
