<template>
  <!-- 컴포넌트 사용 -->
  <MyBtn
    class="heroyp"
    style="color:red;"
    color="#ff0000"
    @hello="log">
    Apple
  </MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'
export default{
  components:{
    MyBtn
  },
  methods:{
    log(){
      this.log('Hello World!')
    }
  }
}
</script>