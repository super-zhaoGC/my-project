<template>
  <div class="block">
    <el-carousel height="195px">
      <el-carousel-item v-for="(item, index) in banner" :key="index">
        <!-- <h3 class="small">{{ item }}</h3> -->
        <img
          :src="item.image"
          alt=""
          class="small"
          style="width: 100%"
          @load="imageLoad"
        />
      </el-carousel-item>
    </el-carousel>
  </div>
</template>
<script>
export default {
  name: "ElementSwiper",
  props: {
    banner: {
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
<style>
.el-carousel__item h3 {
  color: #475669;
  font-size: 14px;
  opacity: 0.75;
  line-height: 150px;
  margin: 0;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  background-color: #d3dce6;
}
</style>