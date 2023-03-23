<template>
  <div id="home_nav">
    <nav-bar><div slot="center">购物街</div></nav-bar>
    <swiper>
      <swiper-item v-for="(item, index) in banners" :key="index">
        <a :href="item.link">
          <img :src="item.image" alt="" />
        </a>
      </swiper-item>
    </swiper>
  </div>
</template>

<script>
import NavBar from "components/common/navBar/NavBar.vue";
import { Swiper, SwiperItem } from "components/common/swiper/index";

import { getHomeMultiData } from "network/home";

export default {
  components: { NavBar, Swiper, SwiperItem },
  name: "Home",
  data() {
    return {
      banners: [],
      recommends: [],
    };
  },
  created() {
    //获取home页面的数据
    getHomeMultiData().then((res) => {
      // console.log(res);
      this.banners = res.data.banner.list;
      this.recommends = res.data.recommend.list;
    });
  },
};
</script>

<style scoped>
#home_nav {
  background-color: var(--color-text);
  color: #fff;
}
</style>