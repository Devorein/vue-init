<template>
  <div class="Card">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: 'Card',
  }
</script>

<style scoped>
div.Card{
  padding: 15px;
  border-radius: 5px;
  box-shadow: 3px 3px 10px #ddd;
  margin: 10px 0px;
}
</style>