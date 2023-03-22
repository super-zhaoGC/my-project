<template>
  <div id="home_nav">
    <nav-bar><div slot="center">购物街</div></nav-bar>
  </div>
</template>

<script>
import NavBar from "components/common/navBar/NavBar.vue";

export default {
  components: { NavBar },
  name: "Home",
  NavBar,
};
</script>

<style scoped>
#home_nav {
  background-color: var(--color-text);
  color: #fff;
}
</style>