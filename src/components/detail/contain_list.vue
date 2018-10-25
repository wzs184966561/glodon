<template>
    <div class="contain_list" v-if="listTxt">
      <ul>
        <li class="box" v-for="(item,index) of listTxt" :key="index" @click="gotodesc($event,item[0],item[1],item[2])">
          <div class="img_box">
            <div><a href="#"><img :src="item[0]" alt=""></a></div>
          </div>
          <h3 v-text="item[1]"></h3>
          <p>售价 ￥{{item[2]}}</p>
          <div class="price">月供：<span>￥{{item[3]}}</span> 起</div>
        </li>
      </ul>
    </div>
</template>
    
<script>
export default {
  props:['listTxt'],
  methods:{
    gotodesc(e,imgSrc,title,price){
      if(e.target.nodeName=="IMG"||e.target.nodeName=="H3"){
        var pushObj={name:'desc',params:{}}
        pushObj.params.imgSrc = imgSrc
        pushObj.params.title = title
        pushObj.params.price = price
        scrollTo(0,0)      
        this.$router.push(pushObj)
      }
    }
  }
}
</script>
    
<style scoped>
*{margin: 0;padding:0;}
.contain_list{width: 1020px;overflow: hidden;}
.contain_list ul{background-color: #fff;width: 1023px;margin-left: -1px;}
.contain_list ul li{float: left;width: 255px;padding: 35px 15px 24px;position: relative;background-color: #fff;border-bottom: 1px solid #f2f2f2;border-left: 1px solid #f2f2f2;}
.img_box{height: 180px;overflow: hidden;position: relative;}
.img_box div{overflow: hidden; width: 214px;height: 180px;display: table;text-align: center;}
.img_box a{display: table-cell;vertical-align: middle;}
.img_box img{width: 180px;}
.box h3{width: 210px;font-size: 14px;overflow: hidden;margin-top: 15px;height: 42px;position: relative;color: #3d3d3d;cursor: pointer;}
.box p{height: 24px;line-height: 24px;font-size: 14px;overflow: hidden;color: #b4b4b4;}
.box .price{font-size: 16px;color: #5faeff;margin-top: 4px;}
.box .price span{font-family: arial;font-style: normal;margin-right: 3px;}
</style>