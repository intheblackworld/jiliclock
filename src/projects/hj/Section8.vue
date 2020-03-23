<template>
  <div class="section7">
    <div
      v-if="!isMobile"
      class="full-bg"
    >
      <img
        v-lazy="require('./s8/img.jpg')"
        alt=""
        class="left"
      >
      <div
        data-aos="fade"
        data-aos-delay="300"
      >
        <img
          v-lazy="require('./s8/timg.png')"
          alt=""
          class="right-img"
        >
      </div>
      <div class="content">
        <div class="title">
          BEST<span>三大聯合<br />建築師事務所</span><br />BRAND
        </div>
        <div class="subtitle">
          成就雋永傳世價值
        </div>
        <div class="desc">
          從宏盛帝寶、仁愛御林園、夢時代商場到W HOTEL，三大聯合建築師事務所將事業版圖擴充至兩岸三地，用心設計出好建築。一絲不茍的規畫，在每件作品的每個細節裡。一磚一瓦，堆砌出你對家最美好的想像。
        </div>
      </div>
      <img
        v-lazy="require('./s8/logo.png')"
        alt=""
        class="logo"
      >
    </div>
    <div
      v-else
      class="m-bg"
    >
      <img
        v-lazy="require('./s8/mo/img.jpg')"
        alt=""
        class="top"
      >
      <div class="bottom">
        <div class="m-content">
          <div class="title">
            BEST<span>三大聯合<br />建築師事務所</span><br />BRAND
          </div>
          <div class="subtitle">
            成就雋永傳世價值
          </div>
          <div class="desc">
            從宏盛帝寶、仁愛御林園、夢時代商場到W HOTEL，三大聯合建築師事務所用一磚一瓦，堆砌出你對家最美好的想像。
          </div>
        </div>
      </div>
      <img
        v-lazy="require('./s8/mo/timg.png')"
        alt=""
        class="m-img"
        data-aos="fade-right"
        data-aos-delay="300"
      >
      <img
        v-lazy="require('./s8/mo/bglogo.png')"
        alt=""
        class="logo"
        data-aos="fade"
        data-aos-delay="400"
      >
    </div>
  </div>
</template>
<style lang="scss" scoped>
@import '@/assets/style/function.scss';

.full-bg {
  background-color: #112d81;
}

.left {
  width: auto;
  height: size(889);
  left: 0;
  right: 0;
  margin: 0 auto;
  position: absolute;
  top: 50%;
  transform: translate(-50%, -50%);
}

.right-img {
  width: auto;
  height: 100vh;
  left: 0;
  right: 0;
  margin: 0 auto;
  position: absolute;
  transform: translateX(50%);
}

.swiper-fullscreen {
  width: auto;
  height: 100vh;
  img {
    width: auto;
    height: 100%;
  }
}

.content {
  position: absolute;
  width: size(520);
  height: 100vh;
  left: 0;
  right: 0;
  margin: 0 auto;
  transform: translateX(65%);
  top: 25%;
  > div {
    width: 100%;
  }
}

.title {
  opacity: 0.8;
  font-family: Impact;
  font-size: size(111);
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 0.99;
  letter-spacing: 6.67px;
  text-align: left;
  color: #db364a;
  margin-bottom: size(30);

  span {
    opacity: 0.5;
    font-size: size(22);
    font-weight: 500;
    font-stretch: normal;
    font-style: normal;
    line-height: 1;
    letter-spacing: 5.47px;
    text-align: left;
    color: #ffffff;
    transform: translateY(-5px);
    display: inline-block;
  }
}

.subtitle {
  font-size: size(35);
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.04;
  letter-spacing: 5.67px;
  text-align: left;
  color: #db364a;
  white-space: nowrap;
  margin-bottom: size(30);
}

.desc {
  width: size(472);
  font-size: size(15);
  font-weight: 300;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.6;
  letter-spacing: 1.19px;
  text-align: left;
  color: #ffffff;
}

.logo {
  position: absolute;
  width: auto;
  height: 100vh;
  left: 0;
  right: 0;
  margin: 0 auto;
  transform: translateX(75%);
}

@media only screen and (max-width: 1280px) and (min-width: 1025px) {
  .fullscreen {
    height: 100vh;
  }
}

/* 螢幕尺寸標準 */
/* 平板尺寸 */
@media only screen and (min-device-width: 768px) and (max-device-width: 1024px) {
  .bg {
  }
}

@media screen and (max-width: 767px) {
  .m-bg {
    background-color: #112d81;
    height: size-m(667);
    position: relative;
  }
  .logo {
    width: size-m(185);
    top: size-m(240);
    left: 0;
    right: 0;
    margin: 0 auto;
    position: absolute;
    z-index: 1;
  }
  .top {
    width: size-m(330);
    margin: 0 auto;
  }
  .bottom {
    width: size-m(330);
    margin: size-m(40) auto;
    display: flex;
    position: relative;
    bottom: 20px;
  }

  .m-img {
    width: 100vw;
    position: absolute;
    right: 0;
    bottom: 0px;
  }
  .m-content {
    width: size-m(317);
  }

  .title {
    font-size: size-m(47);
    letter-spacing: 2.23px;
    span {
      font-size: size-m(14);
    }
  }

  .subtitle {
    font-size: size-m(15);
    margin-bottom: size-m(20);
  }

  .desc {
    width: size-m(330);
    font-size: size-m(12);
  }

  .logo {
    width: 100vw;
    height: auto;
    position: absolute;
    top: auto;
    bottom: 0;
    right: auto;
    left: 0;
    transform: none;
  }
}
</style>
<script>
// @ is an alias to /src
import { isMobile } from '@/utils'

export default {
  name: 'section7',
  data() {
    return {
      isMobile,
    }
  },

  methods: {},

  mounted() {},

  computed: {},
}
</script>
