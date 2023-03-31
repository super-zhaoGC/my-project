<template>
  <div class="recommend">
    <div v-for="(item, index) in recommend" :key="index" class="recommend-item">
      <a :href="item.link">
        <img :src="item.image" alt="" @load="imageLoad" />
        <div>{{ item.title }}</div>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "RecommendsView",
  props: {
    recommend: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  methods: {
    imageLoad() {
      this.$bus.$emit("imageLoad");
    },
  },
};
</script>

<style scoped>
.recommend {
  display: flex;
}
.recommend-item {
  flex: 1;
  text-align: center;
  border-bottom: 10px solid #eeeeee;
  font-size: 12px;
  padding: 10px 0 20px;
}
.recommend-item img {
  width: 70px;
  height: 70px;
}
</style>