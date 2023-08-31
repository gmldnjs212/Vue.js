<template>
  <header>
    <Logo />
    <div class="nav nav-pills">
      <div
        v-for="nav in navigations"
        :key="nav.name"
        class="nav-item">
        <!-- 기존에는 a태그를 사용하여 href에 링크를 넣었었다 -->
        <!-- a태그 대신 vue router에서는 RouterLink라는 컴포넌트를 지원하여
        a태그를 대체하여 보다 더 효율적으로 페이지를 관리할 수 있도록 해준다. -->
        <RouterLink
          :to="nav.href"
          active-class="active"
          class="nav-link">
          {{ nav.name }}
        </RouterLink>
      </div>
    </div>
  </header>
</template>

<script>
import Logo from '~/components/Logo'
export default{
  components:{
    Logo
  },
  data(){
    return{
      navigations: [
        {
          name: 'Search',
          href: '/',
        },
        {
          name: 'Movie',
          href: '/movie',
        },
        {
          name: 'About',
          href: '/about',
        },
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
header{
  height: 70px;
  padding: 0 40px;
  display: flex;
  align-items: center;
  .logo{
    margin-right: 40px;
  }
}
</style>