<template>
  <div class="register">
    <div class="header">
      <div class="fl">
        <div class="left">
          <a href=""><img src="/static/img/reg_login.png" @click.prevent="gohome"></a>
        </div>
        <div class="right">
          <span>欢迎注册</span>
        </div>
      </div>
      <div class="fr">
        已有账号？ <a href="">立即登录</a>
      </div>
    </div>
    <div class="container">
      <div class="title">注册新用户</div>
      <div class="center">
        <img src="/static/img/reg_ma.png">
        <div>扫码下载分期乐APP，30秒提交资料，立获3万元额度</div>
      </div>
    </div>
  </div>  
</template>
  
<script>
export default {
  components: {
  },
  methods:{
    gohome(){
      scrollTo(0,0)
      this.$router.push('home');
    }
  }
}
</script>
  
<style scoped>
.header{width: 1200px;height: 150px;line-height: 150px;margin: 0 auto;position: relative;top: -150px;left: 0;
border-bottom: 1px solid #313131;background: #fff}
.header .fl{float: left;}
.left{float: left;}
.left a{height:40px;display: inline-block;margin-right: 20px;margin-top: 50px;line-height: 40px;padding-right: 20px;border-right: 1px solid #e0e4e8;}
.right{margin-top: 12px;color: #3b9bff;font-size: 20px;float: left;}
.header .fr{float: right;font-size: 14px;}
.header .fr a{color: #3b9bff;}
.container{    width: 1200px;
    margin: 0 auto;    background: #fff;
    min-height: 500px;padding: 0;}
  .container .title{
        height: 50px;
    line-height: 50px;
    background: #f9f9f9;
    border-left: 5px solid #3b9bff;
    font-size: 18px;
    color: #3b9bff;
    padding-left: 45px;
}
.container .center{    text-align: center;
    padding: 60px 0 120px 0;}
.center img{width: 300px;}
.center div{    line-height: 70px;
    font-size: 18px;}
</style>
