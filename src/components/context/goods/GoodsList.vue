<template>
  <div class="goods">
    <goods-list-item
      v-for="(item, index) in goodsList"
      :key="index"
      :goodsItem="goodsList"
    >
    </goods-list-item>
  </div>
</template>

<script>
import GoodsListItem from "./GoodsListItem.vue";

export default {
  name: "GoodsList",
  props: {
    goodsList: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  components: {
    GoodsListItem,
  },
  created() {
    console.log(this.goodsList);
  },
};
</script>

<style scoped>
/* .goods {
  height: 30px;
} */
</style>