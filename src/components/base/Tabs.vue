<template>
  <template v-for="tab in tabs" :key="tab">
    <button @click="$emit('click', tab)">{{tab}}</button>
  </template>
</template>

<script>
  export default {
    name: "Tabs",
    props: ['tabs']
  }
</script>

<style scoped>

</style>