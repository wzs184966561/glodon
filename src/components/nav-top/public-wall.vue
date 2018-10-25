<template>
  <div class="public-wall">
    <h3 v-text="title"></h3>
    <div class="wall">
      <ul>
        <li v-for="(item,index) of txt" :key="index">
          <div class="icon" :style='styles[index]'></div>
          <div class="dashed"></div>            
          <div class="content">
            <h3 v-text="item[0]"></h3>
            <p v-text="item[1]"></p>
            <p v-text="item[2]"></p>
          </div>
        </li>
      </ul>
    </div>
  </div> 
</template>
  
<script>
export default {
  components: {
  },
  props:['title','txt','bgImage','bgPosition'],
  data(){
    return{
      styles:[]
    }
  },
  methods:{
    getStyle(){
      for(var item of this.bgPosition){
        var style = `background-image:${this.bgImage};background-position: ${item}`
        this.styles.push(style)
      }
    }
  },
  mounted(){
    this.getStyle.bind(this)()
  }
};
</script>
  
<style scoped>
.public-wall{width: 1170px;height: auto;margin: auto; color: #47546a;overflow: hidden;}
.public-wall>h3{margin-top: 91px;text-align: center;font-size: 28px;}
.public-wire{padding-top: 97px;border-bottom: 1px solid #f2f3f7;}
.wall ul{padding-top: 82px;}
.wall>ul>li{position: relative;width: 292px;height: auto;float: left;}
.wall li .icon{position: relative; width: 123px;height: 124px;top: 10px;left: 66px;
background:50% no-repeat;}
/* .wall li:nth-child(1) .icon{background-position: 0 -106px;}   
.wall li:nth-child(2) .icon{background-position: -131px -106px;}   
.wall li:nth-child(3) .icon{background-position: -262px -106px;}   
.wall li:nth-child(4) .icon{background-position: -393px -106px;}    */
.wall .dashed{left: 190px;right: 0;position:absolute;top: 70px;width:80%;border-bottom: 1px dashed #c0cdd4;}
.wall li:last-child .dashed{width: 0;}
.wall .content{width: 248px;text-align: center;padding-top: 43px;}
.wall h3{font-size: 18px;margin-bottom: 22px;}
.wall p{font-size: 14px;line-height: 14px;vertical-align: middle;color: #667082}
</style>
