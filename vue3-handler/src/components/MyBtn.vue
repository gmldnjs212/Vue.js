<template>
  <div class="btn">
    <slot></slot>
  </div>
  <h1 @dblclick="$emit('heropy', 123)">
    ABC
  </h1>
</template>

<script>
export default{
  emits:[
    'heropy'
  ]
}
</script>

<style scoped>
  .btn{
    display: inline-block;
    margin: 4px;
    padding: 6px 12px;
    border-radius: 4px;
    background-color: gray;
    color: white;
    cursor: pointer;
  }
</style>