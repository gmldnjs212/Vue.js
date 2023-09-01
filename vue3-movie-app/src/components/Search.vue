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
      placeholder="Search for Movies, Series & more"
      @keyup.enter="apply" />
    <div class="selects">
      <select 
        v-for="filter in filters"
        v-model="$data[filter.name]"
        :key="filter.name"
        class="form-select">
        <option 
          v-if="filter.name === 'year'"
          value="">
          All Years
        </option>
        <option
          v-for="item in filter.items"
          :key="item">
          {{ item }}
        </option>
      </select>
    </div>
    <button
      class="btn btn-primary"
      @click="apply">
      Apply
    </button>
  </div>
</template>

<script>
import axios from "axios"
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
          // year는 가장최신연도부터 1985년까지이다.
          // 일일히 작성하지 않고 반복문을 통해 다룰 것이다.
          name: 'year',
          items: (()=>{
            const years = []
            const thisYear = new Date().getFullYear() // 현재연도
            for (let i=thisYear; i>=1985; i-=1){
              years.push(i) // years라는 배열데이터에 i를 하나씩 넣는다
            }
            return years
          })()
        }
      ]
    }
  },
  methods:{
    async apply(){
      const OMDB_API_KEY = 'f56e64f5'
      // [ OMDBAPI ] Send all data requests to 
      const res = await axios.get(`https://www.omdbapi.com/?apikey=${OMDB_API_KEY}&s=${this.title}&type=${this.type}&y=${this.year}&page=1`)
      console.log(res);
    }
  }
}
</script>
<style lang="scss" scoped>
  .container{
    display: flex;
    > * {
      margin-right: 10px;
      font-size: 15px;
      &:last-child{
        margin-right: 0px;
      }
    }
    .selects{
      display: flex;
      select{
        width:120px;
        margin-right:10px;
        &:last-child{
          margin-right:0px;
        }
      }
    }
    .btn{
      width:120px;
      height:50px;
      font-weight: 700; // bold
      flex-shrink: 0; // 기본값 비율 1, 0이면 감소안함
    }
  }
</style>