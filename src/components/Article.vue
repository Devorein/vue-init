<template>
  <div>
    <h2 v-bind="$attrs">{{title}}</h2>
    <p>{{likes}}</p>
    <p>{{isPublished ? "Published" : "Private"}}</p>
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
      isPublished: Boolean
    },
    inheritAttrs: false
  }
</script>

<style lang="scss" scoped>

</style>