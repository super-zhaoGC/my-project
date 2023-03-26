<template>
  <div class="tab-control">
    <div
      v-for="(item, index) in title"
      :key="index"
      class="tab-control-item"
      :class="{ active: index === currentIndex }"
      @click="tabClick(index)"
    >
      <span>{{ item }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "TabControl",
  props: {
    title: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  data() {
    return {
      currentIndex: 0,
    };
  },
  methods: {
    tabClick(index) {
      this.currentIndex = index;
      this.$emit("tabClick", index);
    },
  },
};
</script>

<style scoped>
.tab-control {
  display: flex;
  text-align: center;
  background-color: #fff;
  font-size: 15px;
  height: 30px;
  margin-top: 5px;
}
.tab-control-item {
  flex: 1;
}
.active {
  color: var(--color-text);
}
.active span {
  border-bottom: 3px solid var(--color-text);
}
.tab-control-item span {
  padding: 5px 5px 5px 2px;
}
</style>