<template>
    <div class="pagebar">
      <span class="pageprev disabled" id="prev" @click="prevPage">上一页</span>
      <a href="" class="active" v-text="pageId+1" @click.prevent="getPage(0)"></a>
      <a href="" v-text="pageId+2" @click.prevent="getPage(1)"></a>
      <a href="" v-text="pageId+3" @click.prevent="getPage(2)"></a>
      <span class="ellipsis">...</span>
      <a href="" @click.prevent="getPage(18)">19</a>
      <span class="pagenext" id="next" @click="nextPage">下一页</span>
      <span class="page-info"><span>1/19</span>页</span>
      <span class="page-info">共<span>1181</span>条数据</span>
      <span class="page-which"><input name="jump" type="text"></span>
      <a class="paging-info page-goto" href="#none">跳转</a>
    </div>
</template>
    
<script>
    
export default {
  components: {
  },
  data(){
    return{
      pageId:0,
      pageMax:19
    }
  },
  methods: {
    nextPage(){
      if(this.pageId<this.pageMax-2){
        prev.className="pageprev" 
        this.pageId++
      }else if(this.pageId<this.pageMax-1){
        next.className="pagenext disabled"
        this.pageId++
      }
      this.$emit('getListTxt',this.pageId%3)
    },
    prevPage(){
      if(this.pageId>1){
        this.pageId--        
        next.className="pagenext" 
      }else if(this.pageId>0){
        this.pageId--
        prev.className="pageprev disabled"
      }
      this.$emit('getListTxt',this.pageId%3)
    },
    getPage(i){
      this.pageId+=i;
      prev.className="pageprev"
      if(i==18){
        next.className="pagenext disabled" 
        this.pageId =18
      }
      this.$emit('getListTxt',this.pageId%3)
    }
  }
}
</script>

<style scoped>
.pagebar{color: gray;margin: 0;padding: 35px 72px 35px 0;zoom: 1;font-size: 12px;text-align: right;vertical-align: middle;}
.pageprev,.pagenext{text-decoration: none;margin: 0 2px;display: inline-block;vertical-align: middle;height: 26px;
line-height: 26px;border: 1px solid #c9c9c9;padding: 0 8px;cursor: pointer;}
.pagebar .disabled{color: #fff;box-shadow: none;background: #d4d4d4;border-color: #d4d4d4;filter: none;cursor: auto;}
.pagebar a{font-weight: 700;padding: 0 8px;text-decoration: none;color: #333;margin: 0 2px;display: inline-block;
vertical-align: middle;height: 26px;line-height: 26px;border: 1px solid #c9c9c9;}
.pagebar .active{color: #fff;background: #3b9bff;border-color: #3b9bff;}
.ellipsis{margin: 0 5px;line-height: 16px;font-weight: 700;}
.page-info{line-height: 28px;margin-right: 5px;height: 28px;color: gray;font-size: 12px;}
.page-which{color: gray;font-size: 12px;}
.page-which input{background-color: #e8e8e8;border: 1px solid #c9c9c9;height: 22px;line-height: 24px;width: 37px;
text-align: center;color: gray;margin: 0;padding: 0;zoom: 1;font-size: 12px;vertical-align: middle;}
.pagebar .page-goto{background-color: #e8e8e8;border: 1px solid #c9c9c9;height: 22px;line-height: 22px;}
</style>