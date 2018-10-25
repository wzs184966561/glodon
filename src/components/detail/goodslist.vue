<template>
    <div class="goodslist">
      <h2><span>商品分类</span></h2>
      <div class="list">
        <ul>
          <li v-for="(item,index) of listTxt" :key="index" @click.prevent="goto(index)">
            <a href="#">
              <i :style="styles[index]"></i>
              <span v-text="item"></span>
            </a>
          </li>
        </ul>
      </div>
    </div>     
  </template>
    
  <script>
  export default {
    components: {
    },
    data(){
      return{
        position:['0 0','-150px -50px','-22px 0','-44px 0','-66px 0','-180px -96px','-100px -96px','-110px 0','-100px -50px','-120px -96px'],
        listTxt:['手机通讯','腕表配饰','电脑办公','相机单反','平板数码','运动户外','服饰鞋靴','箱包潮品','美妆护肤','家电家居'],
        styles:[]
      }
    },
    methods: {
      getStyle(){
        for(var item of this.position){
          var style = `background-position: ${item}`
          this.styles.push(style)
        }
      },
      goto(index){
        this.$emit('goto',index)
      }
    },
    mounted(){
      this.getStyle.bind(this)()
    }
  
  }
  </script>
    
  <style scoped>
  .goodslist{width: 200px;height:488px;margin:0 auto;color: #fff;position: relative;float: left;}
  .goodslist>h2{height: 37px;width: 200px;background-color: #3b9bff;line-height: 37px;text-align: center;color: #fff;
  font-size: 16px;cursor: pointer;position: absolute;top: -37px;left: 0;}
  .list{width: 200px;position: relative;background-color: #fefefe;}
  .list ul li{background: #ededed;border-top: 1px solid #dadada;}
  .list ul li:hover{background: #fff;}
  .list ul li a{color: #4e4e4e;height: 47px;line-height: 47px;display: block;font-size: 15px;
  position: relative;padding-left: 73px;text-decoration: none}
  .list ul li a i{width: 20px;height: 20px;opacity: .7;position: absolute;top: 50%; margin-top: -10px;left: 39px;background: url(/static/img/fs-left.png) no-repeat;
  display: inline-block; background-position: 0 0;}
  </style>
    