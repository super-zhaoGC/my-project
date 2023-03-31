<template>
  <div class="wrapper" ref="wrapper">
    <div class="content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
import BScroll from "better-scroll";

export default {
  name: "Scroll",
  components: {
    BScroll,
  },
  data() {
    return {
      scroll: null,
      msg: "肌肤水分减少了",
    };
  },
  methods: {
    scrollTo(x, y, time = 500) {
      this.scroll.scrollTo(x, y, time);
    },

    refresh() {
      let img = this.$refs.wrapper.getElementsByTagName("img");
      console.log("img", img);
      let count = 0;
      let length = img.length;
      if (length) {
        let timer = setInterval(() => {
          if (count == length) {
            this.scroll.refresh();
            clearInterval(timer);
          } else if (img[count].complete) {
            count++;
          }
        }, 1000);
      }
    },
  },
  mounted() {
    this.scroll = new BScroll(this.$refs.wrapper, {});
    console.log(this.scroll);
  },
  updated() {
    refresh();
  },
};
</script>

<style>
</style>