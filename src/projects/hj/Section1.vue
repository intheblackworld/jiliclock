<template>
  <div class="full-bg">
    <div v-if="!isMobile">
      <div
        class="full-img"
        v-lazy:background-image="require('./s1/bg1.png')"
      ></div>
      <div
        class="full-img"
        v-lazy:background-image="require('./s1/bg2.png')"
        data-aos="fade-right"
        data-aos-delay="300"
      ></div>
      <div
        class="full-img"
        v-lazy:background-image="require('./s1/bg3.png')"
      ></div>
      <img
        src="./s1/t23logo.png"
        alt=""
        class="logo"
        data-aos="fade"
        data-aos-delay="500"
        v-show="slideIndex !== 0"
      >

      <swiper
        :options="swiperOption"
        ref="mySwiper"
        class="swiper-fullscreen logo-swiper"
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
          <img
            src="./s1/t3button.png"
            alt=""
            class="item-img btn"
            v-show="slideIndex === 2"
            v-scroll-to="{ element: `#contact` }"
          >
        </swiper-slide>
      </swiper>
    </div>
    <div v-else>
      <div
        class="full-img"
        v-lazy:background-image="require('./s1/mo/bg1.png')"
      ></div>
      <div
        class="full-img"
        v-lazy:background-image="require('./s1/mo/bg2.png')"
        data-aos="fade-right"
        data-aos-delay="300"
      ></div>
      <div
        class="full-img"
        v-lazy:background-image="require('./s1/mo/bg3.png')"
      ></div>
      <swiper
        :options="swiperOption"
        ref="mySwiper"
        class="swiper-fullscreen logo-swiper"
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
          <img
            src="./s1/mo/t3button.png"
            alt=""
            class="item-img btn"
            v-show="slideIndex === 2"
            v-scroll-to="{ element: `#contact` }"
          >
        </swiper-slide>
      </swiper>
      <img
        src="./s1/mo/t23logo.png"
        alt=""
        class="logo"
        data-aos="fade"
        data-aos-delay="500"
        v-show="slideIndex !== 0"
      >
    </div>
  </div>
</template>
<style lang="scss" scoped>
@import '@/assets/style/function.scss';
.logo {
  position: absolute;
  left: 0;
  height: 100vh;
}

.swiper-fullscreen {
  width: auto;
  height: 100vh;
  img {
    width: auto;
    height: 100%;
  }
}

.logo-swiper {
  width: size(692);
  position: absolute;
  left: 0;
  right: 0;
  transform: translateX(50%);
}

.btn {
  position: relative;
  z-index: 2;
  cursor: pointer;
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
    // height: size_m(1161);
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
  .full-img {
    // &:nth-child(1) {
    //   position: absolute;
    //   z-index: 2;
    //   // mix-blend-mode: screen;
    //   // opacity: 0;
    // }
  }

  .swiper-fullscreen {
    width: auto;
    height: calc(100vh - 63px);
    img {
      width: auto;
      height: 100%;
    }

    .btn {
      width: size-m(183);
      height: auto;
      top: 47vh;
      position: absolute;
      left: 0;
      right: 0;
      margin: 0 auto;
    }
  }

  .logo-swiper {
    width: 100vw;
    position: absolute;
    left: 0;
    right: 0;
    transform: none;
  }

  .logo {
    position: absolute;
    width: 100vw;
    left: 0;
    top: auto;
    height: auto;
    bottom: 0px;
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
          delay: 4000,
          disableOnInteraction: true,
        },
        loop: true,
        direction: 'vertical',
        // effect: 'fade',
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
      },
      slideList: [
        {
          img: require('./s1/t1.png'),
        },
        {
          img: require('./s1/t2.png'),
        },
        {
          img: require('./s1/t3.png'),
        },
      ],

      slideListM: [
        {
          img: require('./s1/mo/t1.png'),
        },
        {
          img: require('./s1/mo/t2.png'),
        },
        {
          img: require('./s1/mo/t3.png'),
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

  created() {
    if (this.isMobile) {
      this.swiperOption.direction = 'horizontal'
    } else {
      this.swiperOption.direction = 'vertical'
    }
  },

  mounted() {},

  computed: {},
}
</script>
