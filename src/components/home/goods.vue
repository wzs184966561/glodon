<template>
  <div class="goots">
      <div class="goodslist clearfix">
        <h2 ><span>商品分类</span></h2>   
        <div class="fs_left show" id="list" >
          <ul >
            <fs-left-item v-for="(item,index) of listTxt" :content="item" :index="index" :key="index"></fs-left-item>
          </ul>
        </div>
        <carousel></carousel>                  
      </div>
    </div>
</template>

<script>
import fsLeftItem from './fs-left-item'
import carousel from './carousel'

export default {
  components: {
    fsLeftItem,
    carousel
  },
  data(){
    return{
      listTxt:['手机通讯','腕表配饰','电脑办公','相机单反','平板数码','运动户外','服饰鞋靴','箱包潮品','美妆护肤','家电家居'],
    }
  },
  methods:{
  }
}
</script>

<style scoped>
.clearfix::after{content:'';display:inline-block;clear:both;}
.goots{background:url(/static/img/gl.jpg) no-repeat top center;}
.goodslist{width: 1200px;height:407px;margin:0 auto;color: #fff;position: relative;}
.fs_left{width:200px;height:407px;background:gray;float: left;font-size:.9rem;position: relative;}
.goodslist>h2{height: 37px;width: 200px;background-color: #3b9bff;line-height: 37px;text-align: center;color: #fff;
font-size: 16px;cursor: pointer;position: absolute;top: -37px;left: 0;}
.goots .show{display:block;}
.goots .hide{display:none;}
.fs_right{width: 800px;height: 407px;background: #bea68d;float: left;font-size:.8rem;position: relative;z-index: 1;}
.fs_right dl{margin: .5rem;overflow:hidden;}
.fs_right dl::after{content:'';display:inline-block;clear:both;}
.fs_right dt,dd{margin-left: 1rem;float: left;}
</style>
