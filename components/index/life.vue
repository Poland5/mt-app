<template>
  <div class="m-life">
    <el-row>
      <el-col :span="14">
        <slide />
      </el-col>
      <el-col :span="4">
        <div class="m-life-pic"></div>
      </el-col>
      <el-col :span="6">
        <div class="m-life-login">
          <h4>
            <img src="//s0.meituan.net/bs/fe-web-meituan/2d05c2b/img/avatar.jpg" />
            <p class="m-life-login-name">Hi！你好</p>
            <p>
              <nuxt-link to="/register">
                <el-button round size="medium">注册</el-button>
              </nuxt-link>
            </p>
            <p>
              <nuxt-link to="/login">
                <el-button round size="medium">立即登录</el-button>
              </nuxt-link>
            </p>
          </h4>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import Slide from '@/components/index/slide'
export default {
  components: {
    Slide
  }
}
</script>

<style lang="scss" scoped>
</style>
