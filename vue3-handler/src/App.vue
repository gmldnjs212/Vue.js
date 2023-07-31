<template>
  <button @click="handler">
    Click me!
  </button>
</template>

<script>
export default{
  methods:{
    handler(event){
      console.log(event);
    }
  }
}
</script>