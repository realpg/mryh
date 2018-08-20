<template>

  <div v-bind:style="{ 'min-height': windowHeight + 'px' }" style="background:#f4f4f4;">
    <img src='../../../static/images/1.png' style='width:750rpx;height:350rpx;'></img>

  <div style='margin:10rpx 25rpx;'>
    <div style='text-align:right;margin-top:20rpx;'>
      <text style='font-size:26rpx;color:#999;font-weight:200;'>共享</text>
      <text style="font-size:26rpx;font-weight:200;color:#FF5959">523626</text>
      <text style="font-size:26rpx;font-weight:200;color:#999;padding-right:30rpx;border-right: 1rpx #999 solid;">元奖金</text>
      <text style="font-size:26rpx;font-weight:200;color:#FF5959;padding-left:30rpx;">38326</text>
      <text style='font-size:26rpx;color:#999;font-weight:200;'>人已参加活动</text>
    </div>
  </div>

  <div style="background:#F5f5f5;height:20rpx;width:750rpx;"></div>


    <div class="bottom flex-row">

      <div @click="switchNavigation" id="1" class="tab">
        <img src="../../../static/images/bottom/easel_n.png" style="width:50rpx;height:50rpx;" alt="">
        <div style="font-size:26rpx;">首页</div>
      </div>

      <div @click="switchNavigation" id="2" class="tab add">
        <div class="picture center-style" style="background:#E21918;width:80rpx;height:80rpx;border-radius: 50%;">
          <img src="../../../static/images/bottom/easel_n.png" style="width:50rpx;height:50rpx;" alt="">
        </div>
        <div style="width:50rpx;height:50rpx;"></div>
        <div style="font-size:26rpx;">每天一画</div>
      </div>

      <div @click="switchNavigation" id="3" class="tab">
        <img src="../../../static/images/bottom/easel_n.png" style="width:50rpx;height:50rpx;" alt="">
        <div style="font-size:26rpx;">我的</div>
      </div>

    </div>
  </div>

</template>

<script>
import card from "@/components/card";

export default {
  data() {
    return {
      motto: "Hello World",
      userInfo: {},
      windowHeight: "",
      navigation_id: 1
    };
  },

  components: {
    card
  },

  methods: {
    bindViewTap() {
      const url = "../logs/main";
      wx.navigateTo({ url });
    },
    switchNavigation(e) {
      var navigation_id = e.currentTarget.id;
      console.log("切换导航：" + JSON.stringify(navigation_id));
      this.navigation_id = navigation_id;
    }
  },

  created() {
    // 调用应用实例的方法获取全局数据
    // this.getUserInfo();
    var windowHeight = wx.getStorageSync("windowHeight");
    this.windowHeight = windowHeight;
    console.log("-------" + windowHeight);
  }
};
</script>

<style scoped>
page {
  background: #f4f4f4;
}

.bottom {
  position: fixed;
  bottom: 0rpx;
  left: 0rpx;
  width: 750rpx;
  height: 90rpx;
  background: #fff;
}

.bottom .tab {
  width: 33%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.bottom .add {
  position: relative;
}

.picture {
  position: absolute;
  bottom: 50rpx;
}
</style>
