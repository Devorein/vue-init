<template>
  <div>
    <UserList>
      <template v-slot:default="slotProps">
        Fullname: {{slotProps.fullname}}
        Username: {{slotProps.username}}
      </template>
    </UserList>
    <div v-for="user in users" :key="'user.'+user.id">
      <User :user="user"/>
    </div>
  </div>
</template>

<script>
import User from "./components/User.vue"
import UserList from "./components/UserList.vue"

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
    User,
    UserList
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
      loggedInUser: users.find(user => user.id === 1),
      users: this.users
    }
  }
}
</script>

<style>

</style>
