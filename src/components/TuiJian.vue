<template>
  <div>
    <div>
      <div class="hezi" v-for="(item, index) in list" :key="index">
        <div class="tu">
          <img :src="item.cover" alt="" />
        </div>
        <div class="xiang">
          <p>{{ item.title }}</p>
          <span>{{ item.author }}</span>
          <br />
          <a>{{ item.dajia }}</a>
        </div>
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
  data() {
    return {
      list: [
        {
          title: "天龙八部",
          author: "金庸 | 推荐值86.3%",
          cover:
            "https://bookcover.yuewen.com/qdbimg/349573/1036314485/150.webp",
          dajia: "大家都在读",
        },
        {
          title: "完美世界",
          author: "陈东 | 推荐值94.3%",
          cover: "https://bookcover.yuewen.com/qdbimg/349573/2952453/150.webp",
          dajia: "大家都在读",
        },
        {
          title: "伪人图鉴",
          author: "真不吃蘑菇 | 推荐值74.3%",
          cover:
            "https://bookcover.yuewen.com/qdbimg/349573/1036919487/90.webp",
          dajia: "大家都在读",
        },
        {
          title: "时间分割",
          author: "手擀面我放盐 | 推荐值87.3%",
          cover:
            "https://bookcover.yuewen.com/qdbimg/349573/1034842298/90.webp",
          dajia: "大家都在读",
        },
        {
          title: "全球冰雪",
          author: "平菇青菜 | 推荐值79.3%",
          cover:
            "https://bookcover.yuewen.com/qdbimg/349573/1037325557/90.webp",
          dajia: "大家都在读",
        },
      ],
    };
  },
};
</script>
<style scoped lang="less">
.hezi {
  width: 100%;
  height: 120px;
  display: flex;
  line-height: 30px;
  margin-top: 20px;
  .xiang {
    margin-left: 20px;
    margin-top: 10px;
    p {
      font-size: 20px;
      font-weight: 600;
    }
    span {
      font-size: 14px;
      font-weight: 400;
      color: gray;
    }
    a {
      font-size: 14px;
      font-weight: 400;
      color: gray;
    }
  }
  .tu {
    width: 90px;
    height: 120px;
    img {
      width: 100%;
      height: 100%;
    }
  }
}
</style>
