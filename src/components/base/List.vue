<template>
  <div v-for="item in items" :key="item.id">
    <slot :item="item"></slot>
  </div>
</template>

<script>
  export default {
    name: 'List',
    props: ['items']
  }
</script>

<style scoped>

</style>