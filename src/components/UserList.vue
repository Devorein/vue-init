<template>
  <h4 v-for="user in users" :key="user.id">
    <slot :username="user.username" :fullname="user.fullname" :totalArticles="user.articles.length"></slot>
  </h4>
</template>

<script>
  export default {
    name: 'UserList',
    inject: ['users']
  }
</script>

<style scoped>

</style>