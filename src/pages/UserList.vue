<template>
  <List :items="users">
    <template v-slot:default="slotProps">
      Fullname: {{slotProps.item.fullname}}
      Username: {{slotProps.item.username}}
      Total Articles: {{slotProps.item.articles.length}}
    </template>
  </List>
</template>

<script>
  import List from "../components/List.vue"
  export default {
    name: 'UserList',
    inject: ['users'],
    components: {
      List
    }
  }
</script>

<style scoped>

</style>