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
    padding: 8px 15px;
    margin: 5px;
    border-radius: 3px;
    font-weight: bold;
    font-size: 20px;
    border: none;
    outline: none;
    cursor: pointer;
  }
</style>