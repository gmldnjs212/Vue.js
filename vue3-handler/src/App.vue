<!-- App.vue -->

<template>
  <h1 @click="increase">
    {{ count }} / {{ doubleCount }}
  </h1>
  <h1 @click="changeMessage">
    {{ message }} // {{ reversedMessage }}
  </h1>
</template>

<script>
export default{
  data(){
    return{
      count: 0,
      message: "Hello World!"
    }
  },
  // computed : 계산된 데이터
  computed:{
    doubleCount(){
      return this.count * 2
    },
    reversedMessage(){
      return this.message.split('').reverse().join('')
    }
  },
  // watch : 명시한 데이터가 변경되면 실행
  watch:{
    // 메시지가 변경되면 새로운 메시지를 받아와서
    // 콘솔에 새로운 메시지를 로그로 찍음
    message(newValue){
      console.log(newValue);
    }
  },
  methods:{
    increase(){
      this.count += 1
    },
    changeMessage(){
      this.message = 'Good?!'
    }
  }
}
</script>