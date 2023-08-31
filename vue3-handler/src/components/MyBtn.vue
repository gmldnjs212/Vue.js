<template>
  <div
    v-bind="$attrs"
    class="btn"
    @click="hello">
    <slot></slot>
  </div>
</template>

<script>
import { onMounted } from 'vue'
export default{
  // 속성을 상속받지 않음
  // -> 그래서 v-bind를 통해 속성을 따로 지정해줄 수 있는것
  inheritAttrs: false,
  props:{
    color: {
      type: String,
      default: 'gray'
    }
  },
  // App.vue의 @hello를 뜻함.
  // MyBtn.vue이라는 뷰컴포넌트 내부에서 
  // hello라는 이벤트를 명시적으로 정의해주고
  // 정의된내용을 methods내부에서 this.$emit을 통해 연결을 해서
  // 실행할 수 있는 구조를 만들어냈다.
  emits: ['hello'],
  // 컴포지션 API코드
  setup(props, context){ // 명시된 순서 == 사용된 순서
    function hello(){
      context.emit('hello') // thist가 아닌 context, $emit의 $는 제거
    }
    onMounted(()=>{
      console.log(props.color) // this가 아닌 props에서 color를 가져옴
      console.log(context.attrs) // this가 아닌 context에서 attrs를 가져오되, $는 제거
    })
    return{
      // 정의된 함수는 반환되어야만 한다
      hello
    }
  }
}
</script>