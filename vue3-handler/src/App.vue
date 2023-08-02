<template>
  <button @click="handler('hi', $event)">
    Click 1
  </button>
  <button @click="handler('what', $event)">
    Click 2
  </button>
</template>

<script>
export default{
  methods:{
    handler(msg){
      console.log(msg);
    }
  }
}
</script>
