<!-- App.Composition.vue -->

<template>
  <h1 @click="increase">
    {{ count }}
  </h1>
  <h1 @click="changeMessage">
    {{ message }}
  </h1>
</template>

<script>
import { ref } from 'vue'

export default{
  setup(){
    let count = ref(0)
    function increase(){
      count.value += 1
    }
    
    let message = ref('Hello World!')
    function changeMessage(){
      message.value = 'Good?!'
    }

    return{
      count,
      message,
      increase,
      changeMessage
    }
  }
}

</script>