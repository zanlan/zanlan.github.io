<template>
  <div id="app">
    <div class="content">
      <div id="nav">
        <div class="nav-itme" :class="active?'active':''" @click="changeTab(true)">开发必备</div>
        <div class="nav-itme" :class="active?'':'active'" @click="changeTab(false)">面试必备</div>
      </div>
    <router-view/>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      active: true,
      logo: require('@/assets/icon_logo.svg')
    }
  },
  mounted () {
    const defaultrouter = location.hash.split('#/')[1]
    if (defaultrouter) {
      this.$router.push({ path: '/' + defaultrouter })
      this.active = false
    }
  },
  methods: {
    changeTab (isYunwei) {
      this.active = !this.active
      this.$router.push({ path: isYunwei ? '/' : '/about' })
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
  padding-top: 30px;
    min-height: 100vh;
    padding-left: calc(100vw - 100%);
    background-image: url('~@/assets/ditu.png');
    background-size: 100% 100%;
    box-sizing: border-box;
    position: relative;
    .content {
      width: 1022px;
      margin: 0 auto;
      #nav{
        .nav-itme:hover{
          cursor: pointer;
        }
        .nav-itme{
          display: inline-block;
          font-size: 20px;
          padding: 5px;
          width: 80px;
          color: #fff;
          list-style: none;
          cursor: pointer;
          text-decoration: none;
          text-align: center;
          margin-right: 40px;
          position: relative;
        }
        .nav-itme.active {
          border-bottom: 4px solid #3278FF;
          color: #3278FF;
        }
      }
    }
}

</style>
