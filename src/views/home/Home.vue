<template>
  <div id="home">
    <nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
    <home-swiper :banner="banners"></home-swiper>
    <recommends-view :recommend="recommends"></recommends-view>
    <feature-view></feature-view>
    <tab-control
      @tabClick="homeTabClick"
      :title="['流行', '新款', '精选']"
      class="tab-control"
    ></tab-control>
    <goods-list :goodsList="goods[currentType].list"></goods-list>
    <ul>
      <li>列表1</li>
      <li>列表2</li>
      <li>列表3</li>
      <li>列表4</li>
      <li>列表5</li>
      <li>列表6</li>
      <li>列表7</li>
      <li>列表8</li>
      <li>列表9</li>
      <li>列表10</li>
      <li>列表11</li>
      <li>列表12</li>
      <li>列表13</li>
      <li>列表14</li>
      <li>列表15</li>
      <li>列表16</li>
      <li>列表17</li>
      <li>列表18</li>
      <li>列表19</li>
      <li>列表20</li>
      <li>列表21</li>
      <li>列表22</li>
      <li>列表23</li>
      <li>列表24</li>
      <li>列表25</li>
      <li>列表26</li>
      <li>列表27</li>
      <li>列表28</li>
      <li>列表29</li>
      <li>列表30</li>
      <li>列表31</li>
      <li>列表32</li>
      <li>列表33</li>
      <li>列表34</li>
      <li>列表35</li>
      <li>列表36</li>
      <li>列表37</li>
      <li>列表38</li>
      <li>列表39</li>
      <li>列表40</li>
      <li>列表41</li>
      <li>列表42</li>
      <li>列表43</li>
      <li>列表44</li>
      <li>列表45</li>
      <li>列表46</li>
      <li>列表47</li>
      <li>列表48</li>
      <li>列表49</li>
      <li>列表50</li>
    </ul>
  </div>
</template>

<script>
import NavBar from "components/common/navBar/NavBar.vue";
import TabControl from "components/context/tabControl/TabControl.vue";
import GoodsList from "components/context/goods/GoodsList.vue";

import HomeSwiper from "./childComp/HomeSwiper.vue";
import RecommendsView from "./childComp/RecommendsView.vue";
import FeatureView from "./childComp/FeatureView.vue";

import { getHomeMultiData, getHomeData } from "network/home";

export default {
  components: {
    NavBar,
    HomeSwiper,
    RecommendsView,
    FeatureView,
    TabControl,
    GoodsList,
  },
  name: "Home",
  data() {
    return {
      banners: [],
      recommends: [],
      goods: {
        pop: { list: [{ age: 1, name: "lilei" }], page: 0 },
        new: { list: [{ age: 2, name: "Bob" }], page: 0 },
        sell: { list: [{ age: 3, name: "pite" }], page: 0 },
      },
      currentType: "pop",
    };
  },
  created() {
    //获取home页面的数据
    this.getMultidataArray();
    this.getHomeDataArray("new");
    this.getHomeDataArray("pop");
    this.getHomeDataArray("sell");
  },
  methods: {
    homeTabClick(index) {
      console.log(index);
      switch (index) {
        case 0:
          this.currentType = "pop";
          break;
        case 1:
          this.currentType = "new";
          break;
        case 2:
          this.currentType = "sell";
          break;
      }
    },

    getMultidataArray() {
      getHomeMultiData().then((res) => {
        // console.log(res);
        this.banners = res.data.banner.list;
        this.recommends = res.data.recommend.list;
      });
    },

    getHomeDataArray(type) {
      const page = this.goods[type].page + 1;
      getHomeData(type, page).then((res) => {
        console.log(res);
        console.log(this.goods[type].list);
        // this.goods[type].list.push(...res.data.list);
        this.goods[type].page += 1;
      });
    },
  },
};
</script>

<style scoped>
#home {
  padding-top: 44px;
}
.home-nav {
  background-color: var(--color-text);
  color: #fff;
  position: fixed;
  left: 0;
  top: 0;
  right: 0;
  z-index: 9;
}
.tab-control {
  position: sticky;
  top: 44px;
}
</style>