<template>
  <div class="home" ref="home">
  <div v-for="(item,index) in arr" :key="index" class="donghua">
    <el-button
    type="danger"
    class="animated bounceIn"
    @click="gotoUrl(item)"
    :href="item.href">{{item.content}}</el-button>
  </div>
  </div>
</template>
<script>
import { arr } from '@/config'
export default {
  name: 'Home',
  data () {
    return {
      arr: arr,
      newimg: require('@/assets/icon_new.svg')
    }
  },
  methods: {
    gotoUrl (item) {
      window.open(item.href)
    }
  }
}
</script>
<style lang='scss' scoped>
.home{
    margin-top: 30px;
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    overflow-y: auto;
    align-content:flex-start;
    a{
      text-decoration: none;
    }
    .item:nth-child(5n){
      margin-right: 0;
    }
    .donghua:hover{
      -webkit-transform: translate3d(0,-3px,0);
      transform: translate3d(0,-3px,0);
    }
    .donghua{
       transition: 0.1s;
       margin-top: 3px;
       margin-right: 10px;
       margin-bottom: 10px;
    }
}
</style>
