<template>
  <div class="card">
    <div class="card-header">
      <slot name="header"></slot>
    </div>
    <div class="card-content">
      <slot name="content"></slot>
    </div>
    <div class="card-footer">
      <slot name="footer"></slot>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Card',
  }
</script>

<style scoped>
div.card{
  padding: 15px;
  border-radius: 5px;
  box-shadow: 3px 3px 10px #ddd;
  margin: 10px 0px;
}

.card-header{
  font-size: 20px;
  text-align: center;
}

.card-footer{
  margin: 20px 0px;
}
</style>