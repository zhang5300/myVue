<template>
    <div class="content">
      <div class="top">
        我的二维码
      </div>
      <div class="qrcode">
        <img class="ewm"  :style="'background-image: url(http://qr.liantu.com/api.php?text=http://bs-mobile.luckyme.com.cn?id='+info.membership_id+')'"></img>
      </div>
      <div class="blank" style="width: 100%;height: 50px"></div>
      <BottomBar :item="3"></BottomBar>
      <GoBack></GoBack>
    </div>
</template>

<script>
  import BottomBar from "../../components/BottomBar";
  import GoBack from "../../components/GoBack";
  export default {
    name: "QR-code",
    components: {
      BottomBar: BottomBar,
      GoBack: GoBack,
    },
    data(){
      return{
        info:{}
      }
    },
    mounted(){
      let info = JSON.parse(localStorage.getItem('info'))
      this.info = info
    }
  }
</script>

<style scoped lang="less">
.content{
  position: fixed;
  width: 100%;
  height: 100%;
  overflow: scroll;
  background-color: #f8f8f8;
  .top {
    width: 100%;
    background-color: white;
    border-bottom: 1px solid gainsboro;
    text-align: center;
    padding: 10px 0;
  }
  .qrcode{
    width: 100%;
    display: flex;
    justify-content: center;
    padding: 50px 0 ;
    .ewm{
      width: 200px;
      max-width: 100%;
      height: 200px;
      background-position: center;
      background-repeat: no-repeat;
      background-size: cover;
    }
  }
}
</style>
