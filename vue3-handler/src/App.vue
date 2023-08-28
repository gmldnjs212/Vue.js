<!-- App.vue -->

<template>
  <h1 @click="increase">
    {{ count }}
  </h1>
  <h1 @click="changeMessage">
    {{ message }}
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
  computed:{
    doubleCount(){
      return this.count
    },
    reversedMessage(){
      return this.message.split('').reverse().join('')
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