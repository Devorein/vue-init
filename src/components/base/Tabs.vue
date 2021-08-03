<template>
  <template v-for="tab in tabs" :key="tab">
    <Button size="medium" :label="tab" @click="$emit('click', tab)"/>
  </template>
</template>

<script>
  import Button from "./Button.vue";
  export default {
    name: "Tabs",
    props: ['tabs'],
    components: {
      Button
    }
  }
</script>

<style scoped>

</style>