<template>
  <div id="app">
    <Header></Header>
    <!--所有的一级路由都在此显示-->
    <router-view></router-view>
    <Footer v-show="!$route.meta.isHideFooter"></Footer>
  </div>
</template>

<script>
import Header from "@/components/Header";
import Footer from "@/components/Footer";

export default {
  name: 'App',
  mounted() {
    //分发请求获取分类列表的异步action
    this.$store.dispatch('getCategoryList')
    this.$store.dispatch('getBannerList')
  },
  components: {
    Header,
    Footer
  }
}
</script>

<style>

</style>
