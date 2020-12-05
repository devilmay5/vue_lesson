<template>
  <div class="topBody">
    aaa
    <router-link :to="{ path: '/Test'}">跳转Test</router-link>
  </div>
</template>

<script>
  export default {
    name: 'Form'
  }
</script>

<style scoped>
  .topBody {
    width: 100%;
    height: 100%;
  }
</style>
