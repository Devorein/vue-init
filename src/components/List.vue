<template>
  <h4 v-for="item in items" :key="item.id">
    <slot :item="item"></slot>
  </h4>
</template>

<script>
  export default {
    name: 'List',
  }
</script>

<style scoped>

</style>