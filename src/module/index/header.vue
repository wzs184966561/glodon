<template>
  <header class="nav">
    <div class="nav-box">
      <div class="logo"><a href="#">GLODON广联达</a></div>
      <div class="search">
        <input id="searchGlobal" maxlength="25" type="text" onkeydown="if(event.keyCode==13){$('#searchIcon').click();return false;}">
        <span id="searchIcon"></span>
      </div>
      <div class="navlist">
        <ul>
          <li v-for="(item,index) of navlist" :key="index">
            <a href="#" v-text="item" class="hover"></a>
            <span v-if="index==1||index==2||index==5"></span>
          </li>
        </ul>
      </div>
    </div>
  </header>
</template>
<script>
export default {
  components:{
  },
  data(){
    return{
      navlist:['首页','产品与服务','解决方案','应用案例','新闻资讯','关于我们']
    }
  },
  methods:{
  },
  mounted(){
    
  }
}
</script>
<style scoped>
.nav{position: fixed;top: 0px;z-index: 20000;background: #fff;width: 100%;min-width: 1200px;height: 60px;border-bottom: 1px solid #ddd;}
.nav-box{width: 1200px;height: 60px;margin: 0 auto;}
.logo{float: left;width: 260px;padding-top: 19px;position: relative;}
.logo a{display: block;overflow: hidden;width: 184px;height: 18px;background: url(/static/img/logo.jpg) no-repeat;text-indent: -999px;}
.search{width: 200px;height: 33px; border: 1px #ccc solid;border-radius: 3px;background: #fafafa;float: right;margin-top: 14px;
position: relative;}
.search input{width: 155px;margin-right: 10px;height: 31px;display: inline-block;border: none;line-height: 31px;font-size: 13px;padding-left: 12px;font-family: "Segoe UI", "Helvetica Neue", Helvetica, sans-serif;background: #fafafa;color: black;}
.search span{display: inline-block;cursor: pointer;background: url(/static/img/sstu.jpg) no-repeat 0 0px;width: 14px;height: 14px;position: relative;top: 1px;}
.navlist{position: relative;float: right;z-index: 1000;height: 60px;text-align: center;padding-right: 35px;}
.navlist ul{width: 100%;height: 100%;list-style-type: none;}
.navlist li {height: 100%;display: block;float: left;font-size: 14px;color: #666;line-height: 60px;cursor: pointer;padding: 0 22px;}
.navlist li a{font-size: 16px;color: #333;line-height: 60px;}
.navlist li .hover{background: #fff;color: #207be6;}
.navlist li span{display: inline-block;width: 12px;height: 10px;background: url(/static/img/dhico.png) no-repeat center center;}
</style>
