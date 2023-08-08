<template>
  <MyBtn>Banana</MyBtn>
  <MyBtn
    :color="colorBlack">
    <span style="color:red">Banana</span>
  </MyBtn>
  <MyBtn
    large
    :color="colorRed">
    Apple
  </MyBtn>
  <MyBtn>Cherry</MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'

export default{
  components:{
    MyBtn
  },
  data(){
    return{
      colorBlack: "#000",
      colorRed: "#F00"
    }
  }
}</script>