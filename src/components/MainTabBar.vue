<template>
  <tab-bar>
    <tab-bar-item path="/home">
      <img slot="item-icon" src="../assets/img/tabBar/icon01.png" alt="" />
      <img
        slot="item-icon-active"
        src="../assets/img/tabBar/icon01_active.png"
        alt=""
      />
      <div slot="item-text">首页</div>
    </tab-bar-item>
    <tab-bar-item path="/category">
      <img slot="item-icon" src="../assets/img/tabBar/icon02.png" alt="" />
      <img
        slot="item-icon-active"
        src="../assets/img/tabBar/icon02_active.png"
        alt=""
      />
      <div slot="item-text">分类</div>
    </tab-bar-item>
    <tab-bar-item path="/cart">
      <img slot="item-icon" src="../assets/img/tabBar/icon03.png" alt="" />
      <img
        slot="item-icon-active"
        src="../assets/img/tabBar/icon03_active.png"
        alt=""
      />
      <div slot="item-text">购物车</div>
    </tab-bar-item>
    <tab-bar-item path="/profile">
      <img slot="item-icon" src="../assets/img/tabBar/icon04.png" alt="" />
      <img
        slot="item-icon-active"
        src="../assets/img/tabBar/icon04_active.png"
        alt=""
      />
      <div slot="item-text">我的</div>
    </tab-bar-item>
  </tab-bar>
</template>

<script>
import TabBar from "../components/tabBar/TabBar";
import TabBarItem from "../components/tabBar/TabBarItem.vue";

export default {
  name: "MainTabBar",
  components: { TabBar, TabBarItem },
};
</script>

<style>
</style>