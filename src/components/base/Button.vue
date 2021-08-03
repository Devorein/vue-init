<template>
  <button @click="$emit('click')" :style="generateButtonStyle()">
    {{label}}
  </button>
</template>

<script>
  export default {
    name: 'Button',
    props: {
      label: {
        type: String,
        required: true
      },
      size: {
        type: String,
        required: false,
        default: "small"
      }
    },
    methods: {
      generateButtonStyle(){
        const size = this.size || 'small';
        const style = {};
        if(size === "small"){
          style.fontSize = '16px';
          style.padding = '5px 12px';
          style.borderRadius = '2px';
          style.margin = '3px'
        } else if(size === "medium"){
          style.fontSize = '18px';
          style.padding = '6px 15px';
          style.borderRadius = '3px';
          style.margin = '5px'
        } else if(size === "large"){
          style.fontSize = '20px';
          style.padding = '8px 18px';
          style.borderRadius = '5px';
          style.margin = '8px'
        }
        return style;
      }
    }
  }
</script>

<style scoped>
  button{
    background-color: #275EFE;
    color: white;
    font-weight: bold;
    border: none;
    outline: none;
    cursor: pointer;
  }
</style>