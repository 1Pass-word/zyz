<template>
  <div>
    <div class="hezi" v-for="(item,index) in list" :key="index">
      <div class="hezi-left">
        <span> {{item.fenlet}} </span>
        <p>
          <a>{{item.yi}}</a><br>
          <span>{{item.yi1}}</span>
          <pre>{{item.yi2}}</pre>
        </p>
      </div>
      <div class="hezi-right">
        <img :src="item.img" alt="">
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data(){
    return {
      list:[
        {
          fenlet:'精品小说',
          img:'https://bookcover.yuewen.com/qdbimg/349573/1021855618/150.webp',
          yi:'1.长相思',
          yi1:'2.剑来',
          yi2:'3.三体'
        },
        {
          fenlet:'历史',
          img:'https://bookcover.yuewen.com/qdbimg/349573/1036332747/150.webp',
          yi:'1.明朝那些事',
          yi1:'2.长安的荔枝',
          yi2:'3.商朝'
        },
        {
          fenlet:'文学',
          img:'https://bookcover.yuewen.com/qdbimg/349573/1020731295/150.webp',
          yi:'1.生活蒙太奇',
          yi1:'2.故事',
          yi2:'3.新摄影笔记'
        },
        {
          fenlet:'人物传记',
          img:'https://bookcover.yuewen.com/qdbimg/349573/1036724189/150.webp',
          yi:'1.邓小平时代',
          yi1:'毛泽东传',
          yi2:'苏东坡传'
        },
        {
          fenlet:'哲学宗教',
          img:'https://bookcover.yuewen.com/qdbimg/349573/1024895162/150.webp',
          yi:'1.道德经',
          yi1:'2.次第花开',
          yi2:'3.传习录'
        }
      ]
    }
  }
};
</script>
<style lang="less" scoped>
.hezi {
  width: 100%;
  height: 175px;
  background-color: #f8f8fa;
  border-radius: 10px;
  display: flex;
  justify-content: space-between;
  margin-top: 20px;
  .hezi-left{
    margin: 20px;
    line-height: 27px;
    span{
        font-size: 20px;
        font-weight: 600;
        color: #333;
      }
      p{
        a{
          font-size: 16px;
          font-weight: 400;
          color: #666;
          margin-right: 10px;
        }
        span{
          font-size: 16px;
          font-weight: 400;
          color: #666;
          margin-right: 10px;
        }
        pre{
          font-size: 16px;
          font-weight: 400;
          color: #666;
          margin-right: 10px;
        }
      }
  }
  .hezi-right{
    img{
      width: 130px;
      border-radius: 0px 10px 10px 0px;
    }
  }
}
</style>
