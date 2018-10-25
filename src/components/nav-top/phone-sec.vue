<template>
  <div class="phone-sec">
    <drop-list></drop-list>
    <div class="container">
      <div class="ewm"></div>
    </div>
  </div>  
</template>
  
<script>
import dropList from '../home/drop-list'
export default {
  components: {
    dropList
  }
}
</script>
  
<style scoped>
.phone-sec{background: url(/static/img/appbg.jpg) no-repeat center top #ecf1f8;
    height: 753px;
    min-width: 1200px;}
.container{   
    position: relative;  width: 1200px;
    margin: 0 auto;}
  .ewm  {width: 318px;
    height: 286px;
    position: absolute;
    background: url(/static/img/ma2.png) no-repeat;
    right: 119px;
    top: 190px;
    overflow: hidden;}
</style>
