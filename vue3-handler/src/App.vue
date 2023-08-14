<template>
  <MyBtn @heropy="log">
    Banana
  </MyBtn>
</template>

<script>
import MyBtn from './components/MyBtn'

export default{
  components:{
    MyBtn
  },
  methods:{
    log(event){
      console.log("Click !"),
      console.log(event);
    }
  }
}
</script>