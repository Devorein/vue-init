<template>
  <List :items="users">
    <template v-slot:default="slotProps">
      <User :user="slotProps.item"/>
    </template>
  </List>
</template>

<script>
  import List from "../components/List.vue"
  import User from "./User.vue"
  export default {
    name: 'UserList',
    inject: ['users'],
    components: {
      List,
      User
    }
  }
</script>

<style scoped>

</style>