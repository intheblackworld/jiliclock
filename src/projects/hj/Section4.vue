<template>
  <div class="section2">
    <div
      v-if="!isMobile"
      class="full-bg"
    >

      <swiper
        :options="swiperOption"
        ref="mySwiper"
        class="left"
        @slideChangeTransitionStart="slideChanged"
      >
        <swiper-slide
          v-for="(slide, index) in slideList"
          :index="index"
          :key="slide.img"
          class="item"
        >
          <img
            :src="slide.img"
            :class="`item-img`"
          />
        </swiper-slide>
      </swiper>
      <div
        data-aos="fade-left"
        data-aos-delay="300"
      >
        <img
          v-lazy="require('./s4/timg.png')"
          alt=""
          class="right-img"
        >
      </div>
      <div class="content">
        <div class="title">
          BEST<br />LIFE
        </div>
        <div class="subtitle">
          暢享雙北的便利
        </div>
        <div class="desc">
          從中正紀念堂到大安森林公園，從中央行政特區到台大校園，人文、學院、藝術、行政、公園、商圈多種機能一次滿足。整個台北市，都是你的後花園。
        </div>
      </div>
      <img
        v-lazy="require('./s4/logo.png')"
        alt=""
        class="logo"
      >
    </div>
    <div
      v-else
      class="m-bg"
    >
      <swiper
        :options="swiperOption"
        ref="mySwiper"
        class="top"
        @slideChangeTransitionStart="slideChanged"
      >
        <swiper-slide
          v-for="(slide, index) in slideListM"
          :index="index"
          :key="slide.img"
          class="item"
        >
          <img
            :src="slide.img"
            :class="`item-img`"
          />
        </swiper-slide>
      </swiper>
      <div class="bottom">
        <div class="m-content">
          <div class="title">
            BEST<br />LIFE
          </div>
          <div class="subtitle">
            暢享雙北的便利
          </div>
          <div class="desc">
            人文、學院、藝術、行政、公園、商圈多種機能一次滿足。整個台北市，都是你的後花園。
          </div>
        </div>
      </div>
      <img
        v-lazy="require('./s4/mo/timg.png')"
        alt=""
        class="m-img"
        data-aos="fade-right"
        data-aos-delay="300"
      >
      <img
        v-lazy="require('./s4/mo/bglogo.png')"
        alt=""
        class="logo"
        data-aos="fade"
        data-aos-delay="300"
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
  width: size(332);
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

.item-img {
  right: 0;
  position: absolute;
  height: size(889);
  width: auto;
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
    height: size-m(360);
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
    width: size-m(145);
  }

  .title {
    font-size: size-m(47);
    letter-spacing: 2.23px;
  }

  .subtitle {
    font-size: size(15);
  }

  .desc {
    font-size: size(12);
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

  .item-img {
    width: 100%;
    height: auto;
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
  name: 'section1',
  mixins: [slider],

  components: {
    swiper,
    swiperSlide,
  },
  data() {
    return {
      isMobile,
      swiperOption: {
        slidesPerView: isMobile ? 1 : 1,
        spaceBetween: isTablet ? 20 : 30,
        slidesPerColumn: isMobile ? 1 : 1,
        allowSlidePrev: isMobile ? true : true,
        allowSlideNext: isMobile ? true : true,
        // centeredSlides: true,
        autoplay: {
          delay: 400000,
          // disableOnInteraction: true,
        },
        loop: true,
        // direction: 'vertical',
        effect: 'fade',
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
      },
      slideList: [
        {
          img: require('./s4/img1.jpg'),
        },
        {
          img: require('./s4/img2.jpg'),
        },
        {
          img: require('./s4/img3.jpg'),
        },
      ],
      slideListM: [
        {
          img: require('./s4/mo/img1.jpg'),
        },
        {
          img: require('./s4/mo/img2.jpg'),
        },
        {
          img: require('./s4/mo/img3.jpg'),
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
      console.log(this.slideIndex)
    },
  },

  mounted() {},

  computed: {},
}
</script>
