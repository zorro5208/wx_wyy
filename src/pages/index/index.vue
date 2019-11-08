<template>
  <div class="index">
    <img class="userImg" v-if="isShow" :src="userInfo.avatarUrl" alt />
    <img class="userImg" v-else src="../../../static/images/logo.jpg" alt />
    <p class="title" v-if="isShow">{{'你好 '+userInfo.nickName}}</p>
    <p class="title" v-else>网易云音乐</p>
    <button class="btn" v-show="!isShow" open-type="getUserInfo" @getuserinfo="getUserInfo">获取用户信息</button>
    <button v-if="isShow" type="primary" @click="toFindMusic">开启小程序</button>
    <van-toast id="van-toast" />
  </div>
</template>

<script>
import Toast from '../../../static/vant-weapp/toast/toast'
export default {
  data() {
    return {
      userInfo:{},
      isShow : false
    };
  },
  components: {
  },

  methods: {
    getUserInfo(data){
      // 如果有数据
      if (data.mp.detail.userInfo) {
        this.userInfo = data.mp.detail.userInfo
        this.isShow = true
      } else {
        this.initGetUser()
      }
    },
    initGetUser(){
      wx.getUserInfo({
        // 成功
        success:(res)=>{
          console.log(res)
          this.userInfo = res.userInfo
          this.isShow = true
        },
        // 失败
        fail:(res)=>{
          Toast.fail('获取失败！');
          
        }
      })
    },
    toFindMusic(){
      wx.switchTab({
        url:'/pages/findMusic/main'
      })
    }
  },
  
  created() {
    // 初始化获取用户信息
    this.initGetUser()
  }
};
</script>

<style lang="less" >
page {
  background: #dc0000;
}
.index {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  .userImg{
    width: 200rpx;
    height: 200rpx;
    border-radius: 200rpx;
    margin: 100rpx 0;
  }
  .title{
    font-size: 60rpx;
    color: #E4E5E5;
    margin-bottom: 350rpx;
  }
  
}
</style>
