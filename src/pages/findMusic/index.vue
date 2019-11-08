<template>
  <div class="index">
    <div class="search_tab">
      <span>
        <i class="iconfont icon-tinggeshiqu"></i>
      </span>
      <span class="search">搜索音乐、歌词、电台</span>
      <span>
        <i class="iconfont icon-yinle"></i>
      </span>
    </div>
    <div class="main">
      <van-tabs :active="active" @change="onChange">
        <van-tab title="个人推荐">内容 1</van-tab>
        <van-tab title="歌单">内容 2</van-tab>
        <van-tab title="主播电台">内容 3</van-tab>
        <van-tab title="排行榜">内容 4</van-tab>
      </van-tabs>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      active: 1
    };
  },

  components: {},

  methods: {
    onChange(event) {
    
  }
  },

  onLoad() {}
};
</script>

<style lang="less" scoped>
.search_tab {
  width: 100%;
  height: 44px;
  border-bottom: 1px solid #ccc;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 10px;
  box-sizing: border-box;
  .iconfont {
    font-size: 26px;
  }
  .search {
    display: inline-block;
    width: 75%;
    height: 30px;
    line-height: 30px;
    border-radius: 30px;
    font-size: 14px;
    text-align: center;
    background: #dadada;
  }
}
</style>
