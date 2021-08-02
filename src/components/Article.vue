<template>
  <div>
    <h2 v-bind="$attrs">{{title}}</h2>
    <p>{{likes}}</p>
    <p>{{published ? "Published" : "Private"}}</p>
    <template v-if="loggedInUser.id ===authorId">
      Created by you
    </template>
  </div>
</template>

<script>
  export default {
    name: 'Article',
    props: {
      title: {
        type: String,
        required: true,
      },
      likes: {
        type: Number,
        default: 0
      },
      authorId: {
        type: Number
      },
      published: Boolean
    },
    inheritAttrs: false,
    inject: ['logged', 'loggedInUser'],
  }
</script>

<style lang="scss" scoped>

</style>