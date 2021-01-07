<template>
  <div id="app">
    <!--<img src="./assets/logo.png">
    <router-view/>-->
    <div class="app-content">
      初始化构建项目+axios
      <h3 class="text">测试vant组件</h3>
      <van-button type="default">默认</van-button>
      <van-button type="primary">主要</van-button>
      <van-button type="info">信息</van-button>
    </div>
  </div>
</template>

<script>
  import http from '@/utils/http';
export default {
  name: 'App',
  mounted() {
    http.get('/website/api/queryTreeList', ).then((res) => {
      if(res.data.success){
        //成功
        this.$toast(res.data.message);
      }else{
        //失败
      }
      console.log(res);
    }).catch((err) => {
      console.log("router-err:", err);
    });
  }
}
</script>

<style lang="scss" scoped>
.app-content{
  color: antiquewhite;
  .text{
    color: #42b983;
  }
}
</style>
