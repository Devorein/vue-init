<template>
  <div>
    <div>
      Fullname: {{fullname}}
    </div>
    <div>
      Username: {{username}}
    </div>
  </div>
</template>

<script>
  export default {
    name: "Greet",
    props: [
      'username',
      'fullname'
    ]
  }
</script>

<style scoped>

</style>