<template>
  <div class="about" ref="about">
  <div v-for="(item,index) in brr" :key="index" class="donghua">
    <el-button
    type="warning"
    class="animated bounceIn"
    @click="gotoUrl(item)"
    :href="item.href">{{item.content}}</el-button>
  </div>
  </div>
</template>
<script>
import { brr } from '@/config'
export default {
  name: 'about',
  data () {
    return {
      brr: brr,
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
.about{
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
