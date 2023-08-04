<template>
  <div class="box">
    <div class="top">
      <svg
        t="1691065526936"
        class="icon"
        viewBox="0 0 1024 1024"
        version="1.1"
        xmlns="http://www.w3.org/2000/svg"
        p-id="1636"
        width="30"
        height="30"
      >
        <path
          d="M448 85.333333a362.666667 362.666667 0 0 1 284.842667 587.178667l193.28 193.28a42.666667 42.666667 0 0 1-60.288 60.373333l-193.365334-193.28A362.666667 362.666667 0 1 1 448 85.333333z m0 85.333334a277.333333 277.333333 0 1 0 0 554.666666 277.333333 277.333333 0 0 0 0-554.666666z"
          fill="#9399a3"
          p-id="1637"
        ></path>
      </svg>
      <input type="text" placeholder="搜索" />
    </div>
    <div class="shujia">
      <div class="shujia1">
        <div class="shujia11">
          <svg
            t="1691066383444"
            class="icon"
            viewBox="0 0 1024 1024"
            version="1.1"
            xmlns="http://www.w3.org/2000/svg"
            p-id="4717"
            width="25"
            height="25"
          >
            <path
              d="M958.72 925.44c-15.36-181.76-139.52-332.16-307.84-386.56C721.28 493.44 768 414.72 768 324.48c0-141.44-115.2-256-256.64-256-141.44 0-256.64 114.56-256.64 256 0 90.24 46.72 168.96 117.12 214.4C204.16 593.28 79.36 743.68 64 925.44c0 3.2-0.64 5.76 0 10.24 1.28 16 15.36 28.8 31.36 28.8l831.36 0c16 0 30.08-12.8 31.36-28.8C959.36 931.2 958.72 928.64 958.72 925.44z"
              p-id="4718"
              fill="#c9c9c9"
            ></path>
          </svg>
          <span>微信用户</span>
          <a>体验卡今日到期</a>
        </div>
        <div class="shujia12">
          <p>反馈</p>
        </div>
      </div>
      <div class="shujia2">
        <div class="shujia21">
          <img
            src="https://bookcover.yuewen.com/qdbimg/349573/1037125335/90.webp"
            alt=""
          />
          <img
            src="https://bookcover.yuewen.com/qdbimg/349573/1037125335/90.webp"
            alt=""
          />
          <img
            src="https://bookcover.yuewen.com/qdbimg/349573/1037125335/90.webp"
            alt=""
          />
        </div>
        <div class="shujia22">
          <span>书架</span>
          <a>></a>
        </div>
      </div>
    </div>
    <div>
      <div class="tabs">
        <div
          v-for="(item, index) in tabs"
          :key="index"
          @click="changeTab(index)"
          :class="{ active: activeTab === index }"
        >
          {{ item.title }}
        </div>
      </div>
      <div class="tab-content">
        <div v-if="activeTab == 0"><tuijian></tuijian></div>
        <div v-if="activeTab == 1">
          <fenlei></fenlei>
        </div>
        <div v-if="activeTab == 2"><paihang></paihang></div>
        <div v-if="activeTab == 3"><wenxue></wenxue></div>
        <div v-if="activeTab == 4"><zhexue></zhexue></div>
      </div>
    </div>
  </div>
</template>
<script>
import paihang from "../components/RanKing.vue";
import fenlei from "../components/FenLei.vue";
import tuijian from "../components/TuiJian.vue";
import wenxue from "../components/WenXue.vue";
import zhexue from "../components/ZheXue.vue";
export default {
  data() {
    return {
      activeTab: 1,
      tabs: [
        { title: "推荐" },
        { title: "分类" },
        { title: "排行" },
        { title: "文学艺术" },
        { title: "哲学社科" },
      ],
    };
  },
  components: {
    paihang,
    fenlei,
    tuijian,
    wenxue,
    zhexue,
  },
  methods: {
    changeTab(index) {
      this.activeTab = index;
    },
  },
};
</script>
<style scoped lang="less">
.tabs {
  font-weight: 600;
  margin-top: 20px;
  display: flex;
  justify-content: space-between;
  font-size: 20px;
  font-family: "华文宋体";
}

.tab-content {
  margin-top: 30px;
}

.active {
  color: #1b88ee;
}
.box {
  padding: 0 20px;
}
.shujia {
  width: 90.2%;
  height: 160px;
  background: #565860;
  margin: auto;
  margin-top: 20px;
  border-radius: 20px;
  padding: 20px;
  .shujia1 {
    display: flex;
    justify-content: space-between;
    align-items: center;
    .shujia11 {
      display: flex;
      align-items: center;
      span {
        font-size: 20px;
        color: #fff;
      }
      a {
        font-size: 16px;
        color: #999fa9;
      }
    }
    .shujia12 {
      float: right;
      margin-right: -20px;
      p {
        display: inline-block;
        width: 60px;
        height: 30px;
        background: #696b70;
        color: #fff;
        text-align: center;
        line-height: 30px;
        border-radius: 30px 0px 0px 30px;
      }
    }
  }
  .shujia2 {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 20px;
    img {
      width: 75px;
      margin-right: 15px;
    }
    .shujia22 {
      display: flex;
      align-items: center;
      span {
        width: 10px;
        color: #fff;
        margin-right: 10px;
      }
      a {
        margin-right: -10px;
        font-size: 20px;
        color: #999fa9;
      }
    }
  }
}
.top {
  width: 100%;
  height: 45px;
  margin: auto;
  input {
    width: 90%;
    height: 100%;
    border-radius: 50px;
    border: none;
    background: #f5f7f9;
    font-size: 20px;
    padding-left: 45px;
  }
  svg {
    position: absolute;
    margin-top: 7px;
    margin-left: 10px;
  }
}
</style>
