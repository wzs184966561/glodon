<template>
  <div class="login">
    <div id="cover-tier" class="cover-tier"></div>
    <div id="pop-tier" class="pop-tier">
      <div class="login">
        <div class="title">
          <span>登录</span>
          <button @click.prevent="close"></button>
        </div>
        <div class="login_box">
          <div class="form">
            <form action="">
              <ul>
                <li>
                  <div class="icon"><i></i></div>
                  <div class="input"><input type="text" placeholder="手机号" id="phone"></div>
                </li>
                <li>
                  <div class="icon2"><i></i></div>
                  <div class="input2">
                    <input type="text" placeholder="短信验证码" id="msg">
                    <div>获取验证码</div>
                  </div>
                </li>
              </ul>
              <button @click.prevent="close">登　录</button>
              <div>注册新用户</div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>  
</template>
  
<script>
export default {
  methods:{
    close(){
      var login = document.querySelector('.login')
      login.style.display="none"
      phone.value=''
      msg.value=''
    }
  },
  mounted(){
    phone.value=''
    msg.value=''
  }
}
</script>
<style scoped>
.cover-tier{overflow: hidden;background-color: #373737;filter: alpha(opacity=50);-moz-opacity: .5;
opacity: .5;z-index: 1022;  position: fixed;  top: 0;left: 0;width: 100%;height: 100%;}
.pop-tier{position: fixed;z-index: 1022;margin: 0 auto;top: 150px;left: 0;right: 0;padding: 0;outline: 0;
border: 0;background: 0 0}
.login{width: 500px;box-shadow: 0 0 5px 0 #878787;margin: 0 auto;}
.login .title{font-size: 18px;color: #666;background-color: #efefef;padding: 0 20px;line-height: 50px;
height: 50px;font-size: 18px;position: relative;}
.login .title span{font-size: 18px;color: #666;line-height: 50px}
.login .title button{width: 25px;height: 25px;background: url(/static/img/close_icon.png) no-repeat;position: absolute;
right: 23px;top: 15px;cursor: pointer;border: 0;}   
.login_box{height: 350px;width: 500px;overflow: auto;background: #fff;}
.form{width: 280px;margin: 40px auto;}
.form ul li{padding: 5px 0;border: 1px solid #f3f3f3;background: #fff;margin-bottom: 15px;overflow: hidden;}
.icon,.icon2{width: 48px;height: 40px;float: left;}
.icon i{ display: block;background: url(/static/img/login_icon2.png) no-repeat;width: 20px;height: 20px;
margin: 10px auto 0;background-position: 0 0;}
.input,.input2{height: 40px;line-height: 40px;float: left;position: relative;}
.input input,.input2 input{border: 0;font-size: 14px;line-height: 14px;padding: 12px;width: 222px;outline: 0;
border-left: 1px solid #f3f3f3;}
.icon2 i{display: block;background: url(/static/img/login_icon2.png) no-repeat;width: 20px;height: 20px;
margin: 10px auto 0; background-position: 0 -21px;}
.input2>div{position: absolute;top: 10px;right: 0;line-height: 20px;padding: 2px 6px;color: #3b9bff;font-size: 14px;
cursor: pointer;}
.form button{width: 100%;margin: 10px 0;background-color: #78baff;color: #abd4ff;border: 0;display: inline-block;
text-align: center;text-decoration: none;cursor: pointer;font-size: 14px;padding: 0 35px;height: 46px;line-height: 46px;}
.form div{font-size: 14px;color: #3b9bff;}
</style> 