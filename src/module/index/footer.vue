<template>
  <div class="footer">
    <div class="ft">
      <dl v-for="(item, index) in ft_list" :key="index">
        <dd v-for="(item, index) in item" :key="index">
          <a href="#"  v-text="item"></a>
        </dd>
      </dl>
      <dl class="callme">
        <dd>全国服务监督电话</dd>
        <dd class="phone">4000-166-166</dd>
      </dl>
    </div>
    <div class="fb">

    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      ft_list:[
        ['用户服务','服务新干线','造价控','用户中心','广小二'],
        ['关于广联达','集团介绍','新闻资讯','联系我们','投资者关系'],
        ['加入广联达','社会招聘','校园招聘','校园招聘'],
        ['关注广联达','官方微信','新浪微博','LinkedIn','Facebook'],
      ]
    }
  }
}
</script>

<style scoped>
.footer{    width: 100%;
    min-width: 1200px;
    background: #242424;
    margin-top: 0px;}
.footer .ft{width: 1080px;
    margin: 0 auto;
    padding: 80px 0 60px 0;overflow: hidden;}
.footer .ft dl{    float: left;
    width: 208px;}
.ft dl dd{    color: #999;
    line-height: 30px;
    font-size: 14px;}
.ft dl dd:first-child a{  font-size: 14px; color: #fff;
    padding-bottom: 6px;}
.ft dl dd a{color: #999;
    font-size: 12px;}
.ft .callme{   float: left;
    width: 208px;height: 124px;padding-left: 32px;
    border-left: 1px #707070 solid;display: flex;
    flex-direction: column;
    justify-content: center;
    padding-bottom: 8px;}
.ft .callme dd{    color: #fff;    line-height: 30px;
    font-size: 14px;}
.ft .callme .phone{font-size: 26px;
    color: #fff;
    line-height: 20px;
    padding-bottom: 6px;
    display: block;}
</style>