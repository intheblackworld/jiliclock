<template>
  <div class="section4">
    <div class="bg">
      <div v-if="!isMobile">
        <img v-lazy="require('./s4/bg.png')" alt class="bg-img" />
        <img
          v-lazy="require('./s4/title.png')"
          alt
          class="bg-img"
          data-aos="fade"
          data-aos-delay="300"
        />
        <div class="block-img" data-aos="fade" data-aos-delay="300">
          <div class="relative">
            <img v-lazy="require('./s4/img.jpg')" alt />
            <div class="block-title">外觀3D示意圖</div>
          </div>
        </div>
        <div class="content">
          <div
            class="desc"
          >天天公園前，一座動感又童趣的建築坐地而生。【京城鳳翔】使用深灰及白色的線條與方格，搭配植栽陽台來營造出建築立面層次感，輕快而不沉重，加上半透光的玻璃，引進自然風光，讓窗外自然環境和建築內的生活搭起對話橋梁。</div>
        </div>
      </div>
      <div v-else>
        <img v-lazy="require('./mo/4/bg.png')" alt class="bg-img" />
        <img v-lazy="require('./mo/4/img.jpg')" alt class="bg-img" data-aos="fade"
          data-aos-delay="300" />
        <img v-lazy="require('./mo/4/title.png')" alt class="bg-img"  data-aos="fade"
          data-aos-delay="400" />
        <div class="content">
          <div
            class="desc"
          >天天公園前，一座動感又童趣的建築坐地而生。【京城鳳翔】使用深灰及白色的線條與方格，搭配植栽陽台來營造出建築立面層次感，輕快而不沉重，加上半透光的玻璃，引進自然風光，讓窗外自然環境和建築內的生活搭起對話橋梁。</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import '@/assets/style/function.scss';
.bg {
  background-size: cover;
  position: relative;
  overflow: hidden;
  position: relative;
  height: calc(100vw * 1320 / 1920);
  display: flex;
  align-items: center;

  > div {
    display: flex;
    align-items: center;
  }
}

.bg-img {
  width: 100vw;
  height: auto;
  position: absolute;
  top: 0;
  left: 0;
  display: block;
  object-fit: cover;
  z-index: 2;

  &:nth-child(1) {
    // position: relative;
  }
}

.block-img {
  position: absolute;
  left: calc(100vw * 37 / 1920);
  top: calc(100vw * 207 / 1920);
  width: calc(100vw * 1124 / 1920);
  z-index: 3;

  img {
    width: 100%;
  }
}

.block-title {
  font-size: size(16);
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.58;
  letter-spacing: 0.48px;
  text-align: right;
  color: #ffffff;
  position: absolute;
  right: size(10);
  bottom: size(10);
}

.content {
  position: absolute;
  width: size(490);
  right: size(159);
  top: size(696);
  z-index: 2;
}

.desc {
  font-size: size(16);
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 2.25;
  letter-spacing: normal;
  text-align: left;
  color: #b7d5d6;
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
  .bg {
    background-size: cover;
    position: relative;
    overflow: hidden;
    position: relative;
    display: block;
    height: size-m(647);

    > div {
      display: block;
    }
  }

  .bg-img {
    width: 100vw;
    position: absolute;
    left: 0;
    top: 0;
    height: auto;
    display: block;
    object-fit: cover;
    z-index: 3;

    // &:nth-child(1) {
    //   position: relative;
    // }
  }

  .content {
    width: size-m(283);
    left: size-m(20);
    margin: 0 auto;
    top: size-m(416);
    z-index: 4;
  }

  .desc {
    font-size: size-m(12);
  }

  .item-title {
    font-size: calc(100vw * 12 / 375);
    font-weight: normal;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.58;
    letter-spacing: 0.48px;
    text-align: right;
    color: #ffffff;
    position: absolute;
    right: 20px;
    bottom: 20px;
  }
}
</style>

<script>
// @ is an alias to /src
import { isMobile, isTablet } from '@/utils'

export default {
  name: 'section4',

  data() {
    return {
      isMobile,
      isTablet,
    }
  },

  methods: {},
}
</script>
