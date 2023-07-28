<template>
  <!-- v-bind:class == :class -->
  <!-- 클릭하면 activate실행 -->
  <!-- activate는 isActive를 true로 만들어줌 -->
  <!-- isActive가 true면 active: true가 되니 스타일 적용 -->
  <h1
    :class="{active: isActive}"
    @click="activate">
    Hello?!({{ isActive }})
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

<style scoped>
  /* scoped : 현재파일(App.vue)에서만 적용되는 스타일 */
  .active{
    color: red;
    font-weight: bold;
  }
</style>