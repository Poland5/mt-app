<template>
  <div class="search-panel">
    <el-row class="m-header-searchbar">
      <el-col :span="3" class="left">
        <img src="//s0.meituan.net/bs/fe-web-meituan/fa5f0f0/img/logo.png" alt="美团" />
      </el-col>
      <el-col :span="15" class="center">
        <div class="wrapper">
          <el-input v-model="search" placeholder="搜索商家和地点" @focus="focus" @blur="blur" @input="input"/>
          <button class="el-button el-button--primary"><i class="el-icon-search"></i></button>
          <dl class="hotPlace" v-if="isHotPlace">
            <dt>热门搜索</dt>
            <dd v-for="(item, index) in hotPlace" :key="index">{{ item }}</dd>
          </dl>
          <dl class="searchList" v-if="isSearchList">
            <dd v-for="(item, index) in searchList" :key="index">{{ item }}</dd>
          </dl>
        </div>
        <p class="suggset">
          <a href="#">广州长隆水上乐园</a>
          <a href="#">广州长隆欢乐世界</a>
          <a href="#">广州长隆野生动物世界</a>
          <a href="#">广州动物园</a>
          <a href="#">广州融创主题乐园</a>
        </p>
        <ul class="nav">
          <li>
            <nuxt-link to="/" class="takeout">美团外卖</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/" class="movie">猫眼电影</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/" class="hotel">美团酒店</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/" class="apartment">名宿/公寓</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/" class="business">商家入驻</nuxt-link>
          </li>
        </ul>
      </el-col>
      <el-col :span="6" class="right">
        <ul class="security">
          <li><i class="refund" /><p class="txt">随时退</p></li>
          <li><i class="single" /><p class="txt">不满意免单</p></li>
          <li><i class="overdue" /><p class="txt">过期退</p></li>
        </ul>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      search: '',
      isFouce: false,
      hotPlace: ['火锅', '火锅', '火锅'],
      searchList: ['故宫', '故宫', '故宫']
    }
  },
  computed: {
    isHotPlace: function() {
      return this.isFouce && !this.search
    },
    isSearchList: function() {
      return this.isFouce && this.search
    }
  },
  methods: {
    focus() {
      this.isFouce = true
    },
    blur() {
      setTimeout(() => {
        this.isFouce = false
      },200)
    },
    input() {
      console.log('input')
    }
  },
};
</script>

<style lang="scss">
</style>
