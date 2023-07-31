<template>
  <h1 @click="activate">
    Hello?!
  </h1>
</template>

<script>
  export default{
    data(){
      return{
        isActive: false
      }
    },
    methods:{
      activate(){
        this.isActive = true
      }
    }
  }
</script>