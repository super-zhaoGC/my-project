<template>
  <div class="goods">
    {{ goodsItem }}
  </div>
</template>

<script>
export default {
  name: "GoodsListItem",
  props: {
    goodsItem: {
      type: Array,
      default() {
        return [];
      },
    },
  },
};
</script>

<style>
</style>