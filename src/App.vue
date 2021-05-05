<template>
  <div id="app">
    <div class="content">
      <div id="nav">
        <div class="nav-itme" :class="active?'active':''" @click="changeTab(true)">频繁使用</div>
        <div class="nav-itme" :class="active?'':'active'" @click="changeTab(false)">求职平台</div>
        <!-- <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link> -->
      </div>
    <router-view/>
    </div>
    <div class="bottombar"><span>©️版权所有：恒大财富有限公司 Hdfax Group 2021-2099</span></div>
  </div>
</template>
<script>
export default {
  data(){
    return{
      active:true
    }
  },
  methods:{
    changeTab(isYunwei){
      this.active = !this.active
      this.$router.push({ path : isYunwei ? '/' : '/about' })
    }
  }
}
</script>
<style lang="scss">
*{
  margin: 0;
  padding: 0;
}
#app{
    width: 100vw;
    height: 100vh;
    background-image: url('~@/assets/ditu.png');
    background-size: 100% 100%;
    overflow: hidden;
    box-sizing: border-box;
    padding-top: 110px;
    .content {
      width: 1000px;
      margin: 0 auto;
      #nav{
        .nav-itme:hover{
          cursor: pointer;
        }
        .nav-itme{
          display: inline-block;
          font-size: 20px;
          padding: 5px;
          width: 100px;
          color: #fff;
          list-style: none;
          border-left: 1px solid #f4f4f4;
          cursor: pointer;
          text-decoration: none;
          text-align: center;
          background-color: #000;
        }
        .nav-itme.active {
          background-color: #9932cd;
        }
      }
    }
    .bottombar {
      width: 100%;
      height: 30px;
      line-height: 30px;
      text-align: center;
      left: 0;
      position: absolute;
      bottom: 0;
      span {
          color: #303030;
          font-size: 12px;
          line-height: 30px;
      }
    }
}

</style>
