<template>
  <tab-bar>
    <tab-bar-item path="/home">
      <img slot="item-icon" src="../../../assets/img/tabbar/home.svg" alt="">
      <img slot="item-icon-active" src="../../../assets/img/tabbar/home-act.svg" alt="">
      <div slot="item-text">首页</div>
    </tab-bar-item>
    <tab-bar-item path="/category">
      <img slot="item-icon" src="../../../assets/img/tabbar/fenlei.svg" alt="">
      <img slot="item-icon-active" src="../../../assets/img/tabbar/fenleiactive.svg" alt="">
      <div slot="item-text">分类</div>
    </tab-bar-item>
    <tab-bar-item path="/cart">
      <img slot="item-icon" src="../../../assets/img/tabbar/gowuche.svg" alt="">
      <img slot="item-icon-active" src="../../../assets/img/tabbar/gouwucheactive.svg" alt="">
      <div slot="item-text">购物车</div>
    </tab-bar-item>
    <tab-bar-item path="/profile">
      <img slot="item-icon" src="../../../assets/img/tabbar/wode.svg" alt="">
      <img slot="item-icon-active" src="../../../assets/img/tabbar/wodeactive.svg" alt="">
      <div slot="item-text">我的</div>
    </tab-bar-item>
  </tab-bar>
</template>

<script>
  import TabBar from '/src/components/common/tabbar/TabBar'
  import TabBarItem from '/src/components/common/tabbar/TabBarItem'

  export default {
    name: "MainTabBar",
    components: {
      TabBar,
      TabBarItem
    }
  }
</script>

<style scoped>

</style>
