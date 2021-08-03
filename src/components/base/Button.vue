<template>
  <button @click="$emit('click')">
    {{label}}
  </button>
</template>

<script>
  export default {
    name: 'Button',
    props: ['label']
  }
</script>

<style scoped>
  button{
    background-color: #275EFE;
    color: white;
    padding: 3px 10px;
    margin: 5px;
    border-radius: 3px;
  }
</style>