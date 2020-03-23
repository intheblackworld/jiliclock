<template>
  <div class="section2">
    <div
      v-if="!isMobile"
      class="full-bg"
    >
      <img
        v-lazy="require('./s2/img.jpg')"
        alt=""
        class="left"
      >
      <div
        data-aos="fade"
        data-aos-delay="300"
      >
        <img
          v-lazy="require('./s2/timg.png')"
          alt=""
          class="right-img"
        >
      </div>

      <div class="content">
        <div class="title">
          BEST<br />LOCATION
        </div>
        <div class="subtitle">
          人氣最旺的 黃金正核心
        </div>
        <div class="desc">
          上接大安 左擁新板，以最從容優雅的姿態，和台北保持最親密的距離。24小時川流不息生活圈，人口最多、生機最強！人氣聚集地，就是未來發展地。
        </div>
      </div>
      <img
        v-lazy="require('./s2/logo.png')"
        alt=""
        class="logo"
      >
    </div>
    <div
      v-else
      class="m-bg"
    >
      <img
        v-lazy="require('./s2/mo/img.jpg')"
        alt=""
        class="top"
      >
      <div class="bottom">
        <div class="m-content">
          <div class="title">
            BEST<br />LOCATION
          </div>
          <div class="subtitle">
            人氣最旺的 黃金正核心
          </div>
          <div class="desc">
            人氣聚集地，就是未來發展地！24小時川流不息生活圈，和台北保持最親密的距離。
          </div>
        </div>
      </div>
      <img
        v-lazy="require('./s2/mo/timg.png')"
        alt=""
        class="m-img"
        data-aos="fade"
        data-aos-delay="300"
      >
      <img
        v-lazy="require('./s2/mo/bglogo.png')"
        alt=""
        class="logo"
      >
    </div>
  </div>
</template>
<style lang="scss" scoped>
@import '@/assets/style/function.scss';

.full-bg {
  background-color: #112d81;
}
.logo {
  position: absolute;
  left: 0;
  height: 100vh;
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
  width: size(464);
  height: 100vh;
  left: 0;
  right: 0;
  margin: 0 auto;
  transform: translateX(63%);
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
    height: size-m(706);
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
  }

  .m-img {
    width: 100vw;
    position: absolute;
    right: 0;
    bottom: 0;
  }

  .m-content {
    width: size-m(180);
  }

  .title {
    font-size: size-m(47);
    letter-spacing: 2.23px;
  }

  .subtitle {
    font-size: size-m(15);
  }

  .desc {
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
import 'swiper/dist/css/swiper.css'

export default {
  name: 'section2',
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
