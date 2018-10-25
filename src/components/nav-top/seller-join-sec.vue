<template>
  <div class="seller-join-sec">
    <carous></carous>
    <div class="wall">
      <h3>现在入驻 即可拥有</h3>
      <div class="first-wall">
        <ul>
          <li v-for="(item,index) of firstWall" :key="index">
            <i></i>
            <h3 v-text="item[0]"></h3>
            <p v-text="item[1]"></p>
          </li>
        </ul>
      </div>
    </div>
    <div class="wire"></div>
    <public-wall :title='title' :txt='secondWall' :bgImage="bgImage" :bgPosition="bgPosition"></public-wall>
    <div class="wire"></div>    
    <div class="wall">
      <div class="third-wall">
        <h3>已合作商家</h3>
        <img src="/static/img/brand.png">
      </div>
    </div>
  </div>  
</template>
  
<script>
import dropList from '../home/drop-list'
import carous from './carou'
import publicWall from './public-wall'
export default {
  components: {
    dropList,
    carous,
    publicWall
  },
  data(){
    return {
      firstWall:[
        ['3000万年轻人购买力','分期消费零负担，释放最强网购欲望'],
        ['线下资源独享','全年100+场次嘉年华，打造高价值品牌'],
        ['365天不中断服务','安全稳定，简单易用，源自十年互联网运营经验'],
        ['平台政策倾斜','海量流量导入+超低服务费，推动业绩指数级增长']
      ],
      secondWall:[
        ['提交申请','卖家阅读入驻须知','点击提交入驻申请'],
        ['平台受理','招商经理受理入驻咨询','确认合作意向'],
        ['提交申请','卖家阅读服务协议','签署相关服务协议'],
        ['开店成功','卖家补全基本信息','店铺上线，开始新生意']
      ],
      title:'如何入驻',
      bgImage:'url(/static/img/iocn_bg.png)',
      bgPosition:['0 -106px','-131px -106px','-262px -106px','-393px -106px']
    }
  }
}
</script>
<style scoped>
.seller-join-sec{background: #fff;}
.wall{width: 1170px;height: auto;margin: auto; color: #47546a;overflow: hidden;}
.wall>h3{margin-top: 91px;text-align: center;font-size: 28px;}
.wire{padding-top: 97px;border-bottom: 1px solid #f2f3f7;}
.first-wall>ul,.second-wall>ul{overflow: hidden;}
.first-wall>ul>li{width: 522px;height: auto;margin: 93px 10px 0 50px;float: left;}
.first-wall i{width: 73px;height: 60px; background-position: 0 0;float: left;margin-right: 57px;
background: url(/static/img/iocn_bg.png) 50% no-repeat;}
.first-wall li:nth-child(1) i{background-position: 0 0;}   
.first-wall li:nth-child(2) i{background-position: -83px 0;}   
.first-wall li:nth-child(3) i{background-position: -156px 0;}   
.first-wall li:nth-child(4) i{background-position: -229px 0;}   
.first-wall h3{font-size: 24px;font-weight: bolder;margin-bottom: 10px;}
.first-wall p{font-size: 18px;color: #667082}
.third-wall h3{margin: 50px 0;text-align: center;font-size: 28px;}
.third-wall img{min-height: 666px;}
</style>
