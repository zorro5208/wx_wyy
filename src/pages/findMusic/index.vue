<template>
  <div class="index">
    <search></search>
    <div class="main">
      <van-tabs :active="active" @change="onChange" tab-active-class="active">
        <van-tab title="个人推荐">内容 1</van-tab>
        <van-tab title="歌单">内容 2</van-tab>
        <van-tab title="主播电台">内容 3</van-tab>
        <van-tab title="排行榜">内容 4</van-tab>
      </van-tabs>
    </div>
  </div>
</template>

<script>
import search from '../../components/search'
export default {
  data() {
    return {
      active: 1
    };
  },

  components: {
    search
  },

  methods: {
    
  },

  onLoad() {}
};
</script>

<style lang="less">

</style>
