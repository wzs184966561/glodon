<template>
  <div class="seller-serve-sev">
    <div class="carousel" @mouseleave="startTimer" @mouseenter="stopTimer">
      <div class="photo" id="photo" style="background-image:url(/static/img/car.jpg)">
      </div>
      <div class="select">
        <ul>
          <li v-for="(item,index) of img" :key="index"><i class="" @mouseover="togglePhoto(index)"></i></li>
        </ul>
      </div> 
    </div>
    <public-wall :title='title' :txt='wallTxt' :bgImage="bgImage" :bgPosition="bgPosition"></public-wall>
    <div class="wire"></div>    
    <div class="download">
      <h3 v-text="dlTitle"></h3>
      <div class="dl_box">
        <ul>
          <li v-for="(item,index) of dlTxt" :key="index">
            <span :style='dlstyles[index]'></span>
            <p v-text="item"></p>
          </li>
        </ul>
      </div>
      <div class="ewm">
        <a href="#"></a>
      </div>
    </div>
    <div class="wire"></div>    
    <div class="investor">
      <h3>投资人介绍</h3>
      <div class="inve_box">
        <ul>
          <li v-for="(item,index) of invetxt" :key="index">
            <div class="top_box">
              <span><img :src="item[0]" alt=""></span>
              <img :src="item[1]">
              <p v-text="item[2]"></p>
            </div>
            <div class="bottom_box">
              <span></span>
              <p v-text="item[3]"></p>
              <span></span>
            </div>
          </li>
        </ul>
      </div>
    </div>
    <div class="wire"></div>  
    <div class="news">
      <h3>媒体报道</h3>
      <div class="news_box">
        <ul>
          <li v-for="(item,index) of newsTxt" :key="index">
            <img :src="item[0]">
            <p v-text="item[1]"></p>
          </li>
        </ul>
      </div>
    </div>  
  </div>
</template>

<script>
import publicWall from './public-wall'
export default {
  components:{
    publicWall
  },
  data(){
    return{
      index:0,
      src:'/static/img/car.jpg',
      img:['/static/img/car.jpg','/static/img/computer.jpg','/static/img/phone.jpg'],
      wallTxt:[
        ['拥抱更庞大的消费人群','先消费后付款的全新消费模式','彻底消除年轻人消费门槛'],
        ['零投入 零成本','免费上门签约','使用过程不产生任何手续费'],
        ['签约办理手续极简','无需购买硬件终端','只需安装手机APP就能开展新生意'],
        ['优质服务平台共赢','提供专人7*24技术支持','背靠大平台共赢好生意']
      ],
      title:'为什么签约分期乐商户',
      bgImage:'url(/static/img/sellerserve.png)',
      bgPosition:['0 0','-115px 0','-232px 0','-348px 0'],
      dlTitle:'下载商户版APP，简单4步，开展新生意',
      dlTxt:['登录商户APP','输入商品生成二维码','用户扫码完成交易','交易成功后，分期乐与你结算'],
      dlPosition:['0 0','-162px -9px','-366px -9px','-552px -9px'],
      dlbgImage:'/static/img/bz.png',
      dlstyles:[],
      invetxt:[
        ['/static/img/jd.png','/static/img/people1.png','京东集团创始人兼董事局主席——刘强东','分期乐&桔子理财是国内互联网小微消费金融的开创者。分期乐是京东全国最大的分销商之一，双方在业务层面有很大的协同效应。'],
        ['/static/img/apoletto.png','/static/img/people2.jpg','俄罗斯DST CEO——尤里·米尔纳','分期乐&桔子理财开创的独特小微消费金融模式非常棒，我们非常看好中国这个领域的未来'],
        ['/static/img/bs.png','/static/img/people3.jpg','贝塔斯曼中国总部首席执行官——龙宇','分期乐&桔子理财是我们遇到的最优秀的团队之一！']
      ],
      newsTxt:[
        ['/static/img/tencent.png','腾讯科技讯12月5日消息，国内年轻人分期购物平台分期乐今日宣布完成新一轮1亿美元的融资。此轮融资由国际顶级投资机构Apoletto（DST创始人Yuri Milner旗下基金）领投，贝塔斯曼、经纬中国和险峰华兴等机构跟投。'],
        ['/static/img/sina.png','新浪科技讯 1月19日上午消息 分期乐集团旗下桔子理财今日宣布其月交易额已突破1亿元。桔子理财是采用了“微金融”运营模式，专注于小微消费金融、债权分散的互联网理财平台。'],
        ['/static/img/wy.png','网易科技讯 目前分期乐公司在北京、上海、广东、深圳等70多个城市建立了营销中心，并率先提供上门自提等额外服务。'],
      ]
    }
  },
  methods:{
    togglePhoto(index){
      this.index =  index;
      photo.style.backgroundImage=`url(${this.img[index]})`;
      var is = document.querySelectorAll(`.select i`);
      for(var item of is){
        item.className = '';
      }
      var i = document.querySelector(`.select ul li:nth-child(${this.index+1}) i`)
      i.className = 'selected';
    },
    setTimer(){
        return setInterval(function(){
        this.index = (this.index+1)%3;
        this.togglePhoto.bind(this)(this.index);
        }.bind(this),2000)
    },
    startTimer(){
      clearInterval(this.timer)      
      this.timer=this.setTimer.bind(this)();
    },
    stopTimer(){
      clearInterval(this.timer)
    },
    getStyle(){
      for(var item of this.dlPosition){
        var style = `background-image:${this.dlbgImage};background-position: ${item}`
        this.dlstyles.push(style)
      }
    }
  },
  mounted() {
    var i = document.querySelector(`.select ul li:nth-child(${this.index+1}) i`)
    i.className = 'selected';
    this.startTimer.bind(this)();
    this.getStyle.bind(this)()
  },
  destroyed() {
    clearInterval(this.timer)
  },
}

</script>

<style scoped>
.seller-serve-sev{background: #fff;}
.carousel{height: 516px;}
.carousel .photo{background:no-repeat top center;height: 516px;}
.wire{padding-top: 97px;border-bottom: 1px solid #f2f3f7;}
.active{display: block;}
.select{ position: absolute;left: 670px;bottom: 20px;font-size: 0;text-align: center;}
.select li{float: left;margin-left: 20px;}
.select i{transition: all .5s ease;position: relative;display: inline-block;width: 13px;height: 13px;margin-right: 1px;border: 2px solid #b9beba;border-radius: 50%;}
.select .selected{background: #71B7FF;border:0;box-shadow: 0 0 0 3px #71B7FF;}
.download{width: 1200px;margin: 0 auto; padding: 60px 0 100px 0;overflow: hidden;}
.download>h3{color: #606060;font-size: 28px;text-align: center;margin-bottom: 70px;}
.dl_box>ul{float: left;margin-top: 8px;}
.dl_box>ul>li{float: left;width: 198px;position: relative;}
.dl_box>ul>li>span{display: block;background-image: url(/static/img/bz.png);width: 146px;height: 87px;margin: 0 auto;}
.dl_box>ul>li>p{position: absolute;left: 60px;margin-top:30px;font-size: 16px;}
.ewm{float: right;margin-right: 20px;}
.ewm a{width: 338px;height: 155px;background: url(/static/img/sign-wc.png) no-repeat;display: inline-block;background-position: -2px 0;}
.ewm a:hover{background-position: -2px -155px;}
.investor{width: 1200px;height: 434px;margin: 20px auto 0;font-size: 12px}
.investor>h3{font-size: 26px;color: #4c4c4c;text-align: center;}
.inve_box{padding-left: 95px;margin-top: 40px;width: 1105px;position: relative;overflow: hidden;}
 .inve_box>ul>li{float: left;text-align: center;position: relative;width: 220px;margin: 0 50px;color: #4c4c4c;}
.top_box{height: 250px;}
.top_box>span{height: 100px;display: block;line-height: 100px;}
.inve_box li:nth-child(1) span>img{width: 86px;height: 32px;}
.inve_box li:nth-child(2) span>img{width: 110px;height: 36px;}
.inve_box li:nth-child(3) span>img{width: 186px;height: 45px;}
.top_box>p{margin-top: 5px;color: #4c4c4c;}
.bottom_box{text-align: left;position: relative;color: #9a9a9a;padding-bottom: 4px;}
.bottom_box>span:first-child{width: 12px;height: 11px;position: absolute;left: 0;top: 0;background: url(/static/img/inveIcon.png) no-repeat;background-position:0px 0;display: inline-block;}
.bottom_box>p{width: 169px;height: 45px;display: inline-block;margin-left: 27px;margin-top: 11px;}
.bottom_box>span:last-child{width: 12px;height: 11px;position: absolute;right: 0;bottom: 0;background: url(/static/img/inveIcon.png) no-repeat;background-position:-20px 0;display: inline-block;}
.news{ width: 1200px;height: 400px;margin: 40px auto 0;}
.news h3{margin-bottom: 80px;font-size: 26px;color: #4c4c4c;text-align: center;}
.news_box{height: 300px;}
.news_box ul{overflow: hidden;}
.news_box ul li{float: left;width: 336px;margin: 0 30px;text-align: center;}
.news_box ul li img{margin-bottom: 34px;}
.news_box ul li p{font-size: 14px;line-height: 25px;text-align: left;padding-left: 11px;color: #5f5f5f}
</style>

