<template>
  <el-container class="layout-default">
    <el-header height>
      <my-header/>
    </el-header>
    <el-main>
      <nuxt />
    </el-main>
    <el-footer>Footer</el-footer>
  </el-container>
</template>

<script>
  import MyHeader from '@/components/public/header/index.vue'
  export default {
    components: {
      MyHeader
    }
  }
</script>
<style lang="scss">
</style>
