<template>
  <List :items="users">
    <template v-slot:default="slotProps">
      <UserCard :user="slotProps.item"/>
    </template>
  </List>
</template>

<script>
  import List from "../components/List.vue"
  import UserCard from "../components/UserCard.vue"
  export default {
    name: 'UserList',
    inject: ['users'],
    components: {
      List,
      UserCard
    }
  }
</script>

<style scoped>

</style>