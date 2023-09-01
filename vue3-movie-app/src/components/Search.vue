<template>
  <div class="container">
    <!-- v-model을 사용하여 양방향 데이터바인딩으로 만들었다 -->
    <!-- input요소에 title이라는 데이터가 연결되었고,
    사용자가 input에 데이터를 입력시 title이라는 데이터에도 갱신이되는 구조가 완성됨 -->
    <!-- class에 form-control을 할당하면 bootstrap에서 제공하는 완성된 ui를 사용할 수 있다. -->
    <input 
      v-model="title"
      class="form-control"
      type="text"
      placeholder="Search for Movies, Series & more" />
  </div>
</template>

<script>
export default{
  data(){
    return {
      title: '',
      type: 'movie',
      number: 10,
      year: '',
      filters: [
        {
          name: 'type',
          items: ['movie','series','episode']
        },
        {
          name: 'number',
          items: [10, 20, 30]
        },
        {
          name: 'year',
          items: (()=>{
            const years = []
            for (let i=2021; i>=1985; i-=1){
              
            }
            retrun []
          })()
        },
        
      ]
    }
  }
}
</script>