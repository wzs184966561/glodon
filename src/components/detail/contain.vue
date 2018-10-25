<template>
    <div class="contain" v-if="txt">
      <div class="top">
        <div class="nav">
          <a href="#">首页 </a>
          <span>></span>
          <a href="#" v-text="txt[0][0].slice(0,1)[0]"></a>
        </div>
        <div class="nav_box">
          <div class="inner_box" v-for="(item,index) of txt[0]" :key="index">
            <div class="title" v-text="item.slice(0,1)[0]"></div>
            <div class="details">
              <a href="#" v-for="(item,index) of item.slice(1)" :key="index" v-text="item"></a>
            </div>
          </div>
        </div>
      </div>
      <div class="filter">
        <div class="fil_left">
          <a href="#" class="selected">默认排序</a>
          <a href="#">价格<i></i></a>
          <a href="#">销量<i></i></a>
          <span>价格：<input type="text"> - <input type="text"></span>
          <a href="#" class="search">搜索</a>
        </div>
        <div class="fil_right">
          <span class="pd">共有 <strong class="c-blue">640</strong> 款产品</span>
          <span class="pd"><span class="c-red">1</span> / <span>100</span></span>
        </div>
      </div>
      <containList :listTxt="listTxt" v-if="listTxt"></containList>
      <pagebar @getListTxt="getListTxt"></pagebar>      
    </div>
</template>
    
<script>
import containList from './contain_list'
import pagebar from './pagebar'
    
export default {
  components: {
    containList,
    pagebar
  },
  data(){
    return{
      listTxt:null,
      pageId:0,
    }
  },
  props:['txt'],    
  methods: {
    getListTxt(pageId){
      var start = pageId*12
      var end = pageId*12+12
      this.listTxt = this.txt[1].slice(start,end);
    }
  },
  watch:{
    txt:function(){
      this.listTxt = this.txt[1].slice(0,12)
    }
  }
}
</script>
    
<style scoped>
.contain{position: relative;width: 1020px;float: right;}
.top{padding: 0 28px;background-color: #fff;font-size: 12px}
.nav{padding: 15px 0;border-bottom: 1px dashed #e6e3e0;color:#8e8f8f;line-height: 26px;}
.nav a{font-size: 14px;color: #8e8f8f;}
.nav span{margin: 0 10px;}
.nav_box{background-color: #FFF;padding: 20px 0;}
.inner_box{padding: 0 80px 0 90px; position: relative;margin-bottom: 12px;}
.inner_box .title{position: absolute;left: 0;top: 0;text-align: right;line-height: 21px;color: #5f5f5f;width: 90px;
font-weight: 700;}
.inner_box .details{height: auto;padding-left: 20px;overflow: hidden;}
.inner_box .details a{height: 21px;line-height: 21px;color: #3b9bff;float: left;padding: 0 6px;margin-right: 12px;
margin-bottom: 8px;}
.inner_box .details .selected{background: #3b9bff;color: #FFF;}
.filter{border-bottom: 1px solid #f2f2f2;background-color: #fcfcfc;overflow: hidden;padding: 8px 15px;font-size: 12px;color: #898989;line-height: 24px;}
.fil_left{float: left;} 
.fil_left a{color: #898989;float: left;margin-right: 35px;}
.fil_left a i{width: 7px;height: 8px;margin-left: 3px;background: url(/static/img/detail_ico.png) no-repeat;display: inline-block;background-position: -90px 0;}
.fil_left span{float: left;}
.fil_left span input{padding: 2px 5px;border: 1px solid #ebebeb;height: 22px;line-height: 16px;width: 55px;}
.fil_left .selected{color:#3b9bff;}
.fil_left .search{margin-right: 10px;border: 1px solid #dfdfdf;height: 22px;line-height: 22px;
background-color: #f7f7f7;padding: 0 10px;margin-left: 10px;float: left;color: #898989;}
.fil_right{float: right;}
.fil_right .pd{margin-right: 20px;}
.fil_right .c-blue{color: #15a4fa;}
.fil_right .c-red{color: #fe4b78;}
</style>