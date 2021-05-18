<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    <home-swiper :banners="banners"></home-swiper>
    <home-recommd-view :recommends="recommends"></home-recommd-view>
    <home-feature-view></home-feature-view>
    <ul>
      <li>haifengzuishuai1</li>
      <li>haifengzuishuai2</li>
      <li>haifengzuishuai3</li>
      <li>haifengzuishuai4</li>
      <li>haifengzuishuai5</li>
      <li>haifengzuishuai6</li>
      <li>haifengzuishuai7</li>
      <li>haifengzuishuai8</li>
      <li>haifengzuishuai9</li>
      <li>haifengzuishuai10</li>
    </ul>
  </div>
</template>

<script>
import NavBar from "../../components/common/navbar/NavBar";
import HomeSwiper from "./childComps/HomeSwiper";
import HomeRecommdView from "./childComps/HomeRecommdView";
import HomeFeatureView from "./childComps/HomeFeatureView";
import {getHomeMultidata} from "../../network/home";

export default {
  name: "home",
  components: {
    NavBar, HomeSwiper, HomeRecommdView, HomeFeatureView
  },
  data() {
    return {
      banners: [],
      recommends: [],
    }
  },
  created() {
    getHomeMultidata().then(res => {
      console.log(res)
      this.banners = res.data.banner.list;
      this.recommends = res.data.recommend.list;
    })
  }
}
</script>

<style scoped>
#home {
  padding-top: 44px
}

.home-nav {
  color: #fff;
  background-color: var(--color-tint);
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  z-index: 9;
}

</style>