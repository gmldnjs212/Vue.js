<template>
  <RouterView />
</template>

<!-- scoped : 현재 스타일태그에 명시된 내용을 
              위의 template에만 영향을 끼치도록하는 옵션
              * 현재 프로젝트에서는 제거됨 -->
<style lang="scss">
  @import "~/scss/main";
</style>