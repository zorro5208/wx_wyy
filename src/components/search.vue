<template>
  <div class="search">
    <!-- <span></span>
    <span></span>
    <span></span>-->
    <search :laceholder="value" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      value:'请输入搜索关键词'
    };
  },
};
</script>

<style lang="less" scoped>
.search {
  height: 44px;
  width: 100%;
}
</style>
