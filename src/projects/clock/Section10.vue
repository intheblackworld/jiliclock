<template>
  <div class="section10">
    <div class="bg">
      <img v-lazy="require('./s10/bg.png')" alt class="bg-img" v-if="!isMobile" />
      <img v-lazy="require('./mo/10/bg.png')" alt class="bg-img" v-if="isMobile" />
      <div class="swiper-button-prev" slot="button-prev">
        <img src="./all/箭頭2.png" alt />
      </div>
      <div class="swiper-button-next" slot="button-next">
        <img src="./all/箭頭1.png" alt />
      </div>
      <swiper
        :options="swiperOption"
        ref="mySwiper"
        data-aos="fade"
        data-aos-delay="200"
        class="swiper-l"
        @slideChangeTransitionEnd="slideChanged"
      >
        <swiper-slide
          v-for="(slide, index) in slideList"
          :index="index"
          :key="slide.img"
          class="item"
        >
          <img :src="slide.img" :class="`item-img`" />
          <div class="item-title" v-html="slide.name"></div>
        </swiper-slide>
      </swiper>
      <transition-group name="slide-fade" mode="out-in">
        <div
          class="content"
          v-for="(slide, index) in slideList"
          v-show="index === slideIndex"
          :key="slide.img"
        >
          <div class="title" v-html="slideList[slideIndex].title"></div>
          <div class="desc" v-html="slideList[slideIndex].desc"></div>
        </div>
      </transition-group>
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
  height: size(740);
  z-index: 2;
}
// .swiper-button-prev, .swiper-button-next {
//   top: 63%;
// }
.bg-img {
  width: 100vw;
  position: absolute;
  top: 0;
  left: 0;
  height: auto;
  display: block;
  object-fit: cover;
  z-index: 0;

  &:nth-child(1) {
    // position: relative;
  }
}

.content {
  width: size(620);
  z-index: 3;
  top: size(270);
  left: size(1128);
  position: absolute;
}

.title {
  font-size: size(40);
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #ffffff;
  margin-bottom: calc(100vw * 15 / 1920);
}

.subtitle {
  font-size: size(24);
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #ffffff;
}

.desc {
  font-size: size(16);
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 2.25;
  letter-spacing: normal;
  text-align: left;
  color: #fff;
}

.swiper-l {
  width: size(1100);
  left: size(0);
  top: size(37);
  position: absolute;
}

.item-img {
  width: 100%;
  height: auto;
}

.item-title {
  font-size: calc(100vw * 16 / 1920);
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

// begin
.slide-fade-leave-to
/* .slide-fade-leave-active for below version 2.1.8 */ {
  // margin-top: 50px !important;
  opacity: 0;
}
// end
.slide-fade-enter {
  margin-top: 10px !important;
  opacity: 0;
}

.slide-fade-enter-active {
  transition: all 0.5s ease-in-out;
}

.slide-fade-leave-active {
  transition: all 0s cubic-bezier(1, 0.5, 0.8, 1);
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
    height: size-m(455);
    display: block;
    z-index: 1;

    > img {
      display: block;
    }

    > div {
      display: block;
    }
  }

  .bg-img {
    width: 100vw;
    position: absolute;
    top: 0;
    left: 0;
    height: auto;
    display: block;
    object-fit: cover;
    z-index: 0;

    // &:nth-child(1) {
    //   position: relative;
    // }
  }

  .swiper-l {
    width: 100vw;
    left: 0;
    top: 0;
  }

  .content {
    width: 90vw;
    top: size-m(282);
    left: size-m(30);
  }

  .title-logo {
    width: 100vw;
    z-index: 10;
  }

  .title {
    font-size: calc(100vw * 22 / 375);
    width: 100%;
  }

  .desc {
    font-size: calc(100vw * 12 / 375);
    width: 100%;
  }
}
</style>

<script>
// @ is an alias to /src
import { isMobile, isTablet } from '@/utils'
import slider from '@/mixins/slider.js'
import 'swiper/dist/css/swiper.css'

import { swiper, swiperSlide } from 'vue-awesome-swiper'

export default {
  name: 'section10',
  mixins: [slider],
  components: {
    swiper,
    swiperSlide,
  },

  data() {
    return {
      isMobile,
      isHide: true,
      swiperOption: {
        slidesPerView: isMobile ? 1 : 1,
        spaceBetween: isTablet ? 20 : 30,
        slidesPerColumn: isMobile ? 1 : 1,
        allowSlidePrev: isMobile ? true : true,
        allowSlideNext: isMobile ? true : true,
        // centeredSlides: true,
        autoplay: {
          delay: 4000,
          disableOnInteraction: true,
        },
        loop: true,
        effect: 'fade',
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
      },
      slideList: [
        {
          img: require('./s10/img1.jpg'),
          title: '衛浴面盆',
          subtitle: '德國國寶品牌 歐洲各國、皇室愛用',
          desc:
            '■ 輕盈堅固，以俐落線條來表現時尚優雅之美<br />■ 簡潔設計能完美融入各種風格的浴室設計<br />■ 使用特殊的塗層更耐用持久，打掃清潔更輕鬆',
        },
        {
          img: require('./s10/img2.png'),
          title: '阿拉斯加HEPA 全熱交換器',
          subtitle: '供應新鮮氧氣　兼具除蟎殺菌',
          desc:
            '■ 具排氣、進氣功能，不開窗也有自然通風效果<br />■ 配備HEPA過濾網、奈米光觸媒殺菌燈<br />■ 醫療級空氣清淨效果，將過敏原排除屋外',
        },

        {
          img: require('./s10/img3.jpg'),
          title: '隔音地墊',
          subtitle: '豪宅建案御用 隔音公法首選',
          desc:
            '■ 最先進技術與製程打造MIT無毒環保隔音墊<br/>■ 不含甲醛，不會逸散對人體有害物質<br/>■ 接縫面積少、施工速度更快，貼合面也更平整',
        },
        {
          img: require('./s10/img4.jpg'),
          title: '全智能馬桶',
          subtitle: '全球衛浴領導 喜來登酒店選用',
          desc:
            '■ 西班牙百年品牌，銷售遍及135國，深受使用者愛戴<br/>■ 全球唯一全瓷化無死角一體成形馬桶，易清潔又時尚<br/>■ 源自歐洲的強勁沖水技術，極少量水即可帶走髒汙',
        },
        {
          img: require('./s10/img5.jpg'),
          title: '大雅廚具',
          subtitle: '聖瑪格麗特石英石　100%產自義大利',
          desc:
            '■ 吸水率只有0.07%，有極高的抗腐蝕能力<br/>■ 接觸高溫不易形成凹痕和焦斑，最高達莫氏硬度7<br/>■ 檯面無需打磨，日常只需用清水及肥皂沖洗清潔',
        },
      ],
    }
  },

  methods: {
    slideChanged(e) {
      const swiper = this.$refs.mySwiper.swiper
      if (swiper.isEnd) {
        this.slideIndex = 0
      } else if (swiper.isBeginning) {
        this.slideIndex = swiper.slides.length - 3
      } else {
        this.slideIndex = swiper.activeIndex - 1
      }
    },
  },
}
</script>
