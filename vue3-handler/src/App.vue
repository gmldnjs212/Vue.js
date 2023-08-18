<template>
  <h1 ref="hello">
    Hello World!
  </h1>
</template>

<script>
export default{
  mounted(){
    console.log(this.$refs.hello);
    console.log(this.$refs.hello.textContent);
  }
}
</script>