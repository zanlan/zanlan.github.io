<template>
  <div class="home">
    <a v-for="(item,index) in arr" :key="index"  :href="item.href" target="_blank" class="item">
      <img :src="item.img">
      <div >
        <span >{{item.content}}</span>
      </div>
    </a>
  </div>
</template>

<script>
import {arr} from '@/config'
export default {
  name: 'Home',
  data(){
    return{
      arr:arr
    }
  }
}
</script>
<style lang='scss' scoped>
.home{
    margin-top: 20px;
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    .item {
        width:190px;
        height:120px;
        text-align:center;
        background:#00f;
        background-color:#e6e8fa;
        cursor:pointer;
        box-shadow: 0 0 3px rgb(0,0,0);
        margin-right:3px;
        margin-left:3px;
        margin-bottom:6px;
        color:#303030;
        img{
          margin-top: 10px;
          width: 80px;
          height: 80px;
        }
    }
}
</style>
