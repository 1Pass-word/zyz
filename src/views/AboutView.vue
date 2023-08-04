<template>
  <div id="root">
    <div>
      <div class="tab-header">
        <div
          v-for="(tab, index) in tabs"
          :key="index"
          :class="['tab', { active: activeTab === index }]"
          @click="changeTab(index)"
        >
          {{ tab.title }}
        </div>
      </div>
      <div class="tab-content">
        <div
          v-for="(tab, index) in tabs"
          :key="index"
          v-show="activeTab === index"
        >
          {{ tab.content }}
        </div>
      </div>
    </div>
    <hr />
    <div class="slider">
      <div
        class="slider-container"
        :style="{ transform: `translateX(-${currentIndex * 100}%)` }"
      >
        <div class="slide" v-for="(slide, index) in slides" :key="index">
          <img :src="slide.image" :alt="slide.caption" />
        </div>
      </div>
      <div class="slider-dots">
        <span
          class="dot"
          v-for="(slide, index) in slides"
          :key="index"
          :class="{ active: currentIndex === index }"
          @click="changeSlide(index)"
        ></span>
      </div>
    </div>
    <button @click="zuo()" class="zuo">⬅️</button>
    <button @click="you()" class="you">➡️</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      currentIndex: 0,
      slides: [
        {
          image:
            "https://img0.baidu.com/it/u=293428944,389988821&fm=253&fmt=auto&app=138&f=JPEG?w=889&h=500",
          caption: "Slide 1",
        },
        {
          image:
            "https://img0.baidu.com/it/u=937072262,2445742246&fm=253&fmt=auto&app=120&f=JPEG?w=1280&h=800",
          caption: "Slide 2",
        },
        {
          image:
            "https://img1.baidu.com/it/u=94904965,608097738&fm=253&fmt=auto&app=138&f=JPEG?w=889&h=500",
          caption: "Slide 3",
        },
        {
          image:
            "https://img2.baidu.com/it/u=2817526356,1385623556&fm=253&fmt=auto&app=120&f=JPEG?w=1280&h=800",
          caption: "Slide 4",
        },
        {
          image:
            "https://img2.baidu.com/it/u=3790341833,2407789859&fm=253&fmt=auto&app=120&f=JPEG?w=1422&h=800",
          caption: "Slide 5",
        },
      ],
      activeTab: 0,
      tabs: [
        { title: "Tab 1", content: "This is tab 1 content" },
        { title: "Tab 2", content: "This is tab 2 content" },
        { title: "Tab 3", content: "This is tab 3 content" },
      ],
    };
  },
  mounted() {
    this.startAutoPlay();
  },
  methods: {
    you() {
      this.currentIndex += 1;
      if (this.currentIndex >= this.slides.length) {
        this.currentIndex = 0;
      }
    },
    zuo() {
      this.currentIndex -= 1;
      if (this.currentIndex < 0) {
        this.currentIndex = this.slides.length - 1;
      }
    },
    changeSlide(index) {
      this.currentIndex = index;
    },
    startAutoPlay() {
      setInterval(() => {
        this.currentIndex = (this.currentIndex + 1) % this.slides.length;
      }, 2500);
    },
    changeTab(index) {
      this.activeTab = index;
    },
  },
};
</script>
<style scoped>
.tab-header {
  width: 50%;
  display: flex;
  justify-content: space-between;
  margin: auto;
}

.tab {
  padding: 10px;
  cursor: pointer;
}

.tab.active {
  background-color: #ccc;
}

.tab-content {
  width: 50%;
  margin: auto;
  margin-top: 10px;
  text-align: center;
}

.slider {
  position: relative;
  width: 100%;
  height: 500px;
  overflow: hidden;
}

.slider-container {
  display: flex;
  transition: transform 0.5s;
}

.slide {
  flex: 0 0 100%;
}

.slide img {
  width: 100%;
  object-fit: cover;
}

.slider-dots {
  position: absolute;
  bottom: 10px;
  left: 50%;
  transform: translateX(-50%);
}

.dot {
  display: inline-block;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background-color: #ccc;
  margin: 0 5px;
  cursor: pointer;
}

.dot.active {
  background-color: #000;
}

.zuo {
  position: absolute;
  top: 40%;
  left: 2%;
  width: 100px;
  height: 100px;
  border-radius: 50%;
  font-size: 55px;
  border: none;
  background: none;
}

.you {
  position: absolute;
  top: 40%;
  right: 2%;
  width: 100px;
  height: 100px;
  border-radius: 50%;
  font-size: 55px;
  border: none;
  background: none;
}
</style>
