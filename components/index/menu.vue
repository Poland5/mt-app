<template>
  <div class="m-menu">
    <dl class="nav" @mouseleave="mouseleave">
      <dt>全部分类</dt>
      <dd v-for="(item, index) in menu" :key="index" @mouseenter="mouseenter">
        <i :class="item.type" />
        {{ item.name }}
        <span class="arrow" />
      </dd>
    </dl>
    <div class="detail" v-if="kind" @mouseenter="sover" @mouseleave="sout">
      <section v-for="(item, index) in curdetail.child" :key="index">
        <h4>{{ item.title }}</h4>
        <span v-for="(subItem, index) in item.child" :key="index">子项</span>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      kind: '',
      menu: [
        {
          type: "food",
          name: "美食",
          child: [
            {
              title: "美食",
              child: ["代金券", "代金券", "代金券", "代金券"]
            },
            {
              title: "美食",
              child: ["代金券", "代金券", "代金券", "代金券"]
            }
          ]
        },
        {
          type: "takeout",
          name: "外卖",
          child: [
            {
              title: "外卖",
              child: ["代金券", "代金券", "代金券", "代金券"]
            }
          ]
        }
      ]
    };
  },
  computed: {
    curdetail() {
      return this.menu.filter(item => item.type === this.kind)[0]
    }
  },
  methods: {
    mouseleave() {
      let self = this
      this.timer = setTimeout(function() {
        self.kind = ''
      }, 150)
    },
    mouseenter(e) {
      this.kind = e.target.querySelector('i').className
    },
    sover() {
      clearTimeout(this.timer)
    },
    sout() {
      this.kind = ''
    }
  }
};
</script>

<style lang="scss">
</style>
