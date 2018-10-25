<template>
  <div class="carousel" @mouseleave="startTimer" @mouseenter="stopTimer">
    <div class="photo" >
      <div class="outer_box active" id="box1">
        <div class="inner_box">
          <h1>开始新生意</h1>
          <h3>入驻年轻人购物大平台，官方扶持轻松赢得未来</h3>
        </div>
        <div class="btn"><a href="#">立即入驻</a></div>
        <img src="/static/img/banner01.jpg">
      </div>
      <div class="outer_box" id="box2">
        <div class="inner_box ">
          <h1>开始新生意</h1>
          <h3>核心电商能力独家开放，帮助企业紧握市场走向</h3>
        </div>
        <div class="btn"><a href="#">立即入驻</a></div>
        <img src="/static/img/banner02.jpg">
      </div>
    </div>
     <div class="arrows_left" @click="togglePhoto"><img src="/static/img/arrow-left.png"></div>    
    <div class="arrows_right" @click="togglePhoto"><img src="/static/img/arrow-right.png"></div>
    <div class="select">
      <ul>
        <li><i class="selected" @click="togglePhoto"></i></li>
        <li><i class="" @click="togglePhoto"></i></li>
      </ul>
    </div> 
  </div>
</template>

<script>
export default {
  data(){
    return{
      lino:0,
      imgClass:'show',
      timer:null
    }
  },
  methods:{
    togglePhoto(){
      if(box1.className=='outer_box'){
        box1.className='outer_box active'
        box2.className='outer_box'
      }
      else{
        box2.className='outer_box active'
        box1.className='outer_box'
      }
      this.toggleList.bind(this)();
    }, 
    toggleList(){
      if(this.lino=='1'){
        var i1 = document.querySelector(`.select li:nth-child(${this.lino}) i`)
        var i2 = document.querySelector(`.select li:nth-child(${this.lino+1}) i`)
        i1.className = 'selected'
        i2.className = ''
        this.lino=0        
      }else{
        var i1 = document.querySelector(`.select li:nth-child(${this.lino+1}) i`)
        var i2 = document.querySelector(`.select li:nth-child(${this.lino+2}) i`)
        i1.className = ''
        i2.className = 'selected'
        this.lino=1        
      }
    },   
    setTimer(){
        return setInterval(function(){
        this.togglePhoto.bind(this)();
        }.bind(this),2000)
    },
    startTimer(){
      clearInterval(this.timer)      
      this.timer=this.setTimer.bind(this)();
    },
    stopTimer(){
      clearInterval(this.timer)
    }
  },
  mounted() {
    this.startTimer.bind(this)();
  },
  destroyed() {
    clearInterval(this.timer)
  },
}

</script>

<style scoped>
@keyframes fadeInDown{
  from{opacity: 0;margin-top:0px;}
  to{opacity: 1;margin-top:20px;}
}
.outer_box{height: 400px;background: gray;position: relative; display: none;}
.inner_box{position: absolute;width: 100%;left: 0;right: 0;top: 48%;margin-top: -6%;text-align: center;}
.inner_box h1{color: #fff;font-size: 52px;font-weight: bolder;letter-spacing: 5px;margin-top: 0px;-webkit-animation: fadeInDown 1s both;animation: fadeInDown 1s both;}
.inner_box h3{color: #fff;font-size: 30px;letter-spacing: 3px;-webkit-animation: fadeInDown 1s .3s both;animation: fadeInDown 1s .3s both;}
.outer_box .btn{position: absolute;left: 0;right: 0;bottom: 15%;margin: 0 auto;text-align: center;}
.outer_box .btn a{display: inline-block;text-decoration: none;width: 160px;height: 60px; margin: auto;color: #fff;font-size: 24px;text-align: center;line-height: 60px;background: #3b9bff;border-radius: 4px;}
.outer_box img{display: block;max-width: 100%;height: auto;}
.active{display: block;}
.carousel .arrows_left{position: absolute;top: 160px;left: 100px;width: 40px;height: 100px;line-height: 95px;text-align: center;background-color: rgba(0,0,0,.2);cursor: pointer;}
.carousel .arrows_right{position: absolute;top: 160px;left: 1200px;width: 40px;height: 100px;line-height: 95px;text-align: center;background-color: rgba(0,0,0,.2);cursor: pointer;}
.select{ position: absolute;left: 670px;bottom: 20px;font-size: 0;text-align: center;}
.select li{float: left;margin-left: 20px;}
.select i{transition: all .5s ease;position: relative;display: inline-block;width: 13px;height: 13px;margin-right: 1px;border: 2px solid #b9beba;border-radius: 50%;}
.select .selected{background: snow;border:0;box-shadow: 0 0 0 3px rgba(255, 255, 255, 0.5);}
</style>

