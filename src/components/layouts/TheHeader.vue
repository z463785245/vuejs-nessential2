<template>
  <div class="navbar navbar-default topnav">
    <div class="container">
      <div class="navbar-header">
        <button type="button" class="navbar-toggle" @click="toggleNav">
          <span class="sr-only">Toggle navigation</span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
        </button>

        <router-link to="/" class="navbar-brand">
          <span class="title">{{ logo.title }}</span>
          <img :src="logo.src" :alt="logo.title" style="width:20px;height:20px;">
        </router-link>
      </div>

      <div id="top-navbar-collapse" :class="['collapse', 'navbar-collapse', { in: showCollapsedNav }]">
        <ul class="nav navbar-nav">
          <li v-for="(item, index) in navList" :key="item.index" :class="{ active: index === activeNavIndex }">
            <a href="#" @click="changeNavIndex(index)">{{ item }}</a>
          </li>
        </ul>
        <div class="navbar-right">
            <TheEntry/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TheEntry from '@/components/layouts/TheEntry'
export default {
  name: 'TheHeader',
  components: {
      TheEntry
  },
  data() {
    return {
      logo: {
        src: "http://www.cm24.com.cn/themes/cm2020/public/images/index/erweima.png",
        title: 'Learnku Vue.js'
      },
      navList: ['社区', '头条', '问答', '教程'],
      activeNavIndex: 0,
      showCollapsedNav: false
    }
  },
  // beforeCreate() {
  //   this.uploadsUrl = 'https://learnku.com/vuejs/uploads/'
  // },
  methods: {
    changeNavIndex(index) {
      this.activeNavIndex = index
    },
    toggleNav() {
      this.showCollapsedNav = !this.showCollapsedNav
    }
  }
}
</script>

<style scoped>
.title { display: none;}
.navbar-default .navbar-nav > .active > a { background: rgba(0,0,0,.03);}
</style>