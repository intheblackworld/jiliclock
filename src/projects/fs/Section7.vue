<template>
  <div class="section7">
    <div class="bg">
      <div v-if="!isMobile">
        <img
          v-lazy="require('./s7/bg.png')"
          alt
          class="bg-img"
        />
        <img
          v-lazy="require('./s7/box.png')"
          alt
          class="bg-img"
        />
        <img
          v-lazy="require('./s7/box1.png')"
          alt
          class="bg-img"
        />
        <div
          class="block-img block-img-1"
          data-aos="fade"
          data-aos-delay="300"
        >
          <div class="relative">
            <img
              v-lazy="require('./s7/img1-1.jpg')"
              alt
            />
            <div class="block-title">業績實景</div>
          </div>
        </div>
        <div
          class="block-img block-img-2"
          data-aos="fade"
          data-aos-delay="300"
        >
          <div class="relative">
            <img
              v-lazy="require('./s7/img1-2.jpg')"
              alt
            />
            <div class="block-title">健身房3D示意圖</div>
          </div>
        </div>
        <div
          class="block-img block-img-3"
          data-aos="fade"
          data-aos-delay="300"
        >
          <div class="relative">
            <img
              v-lazy="require('./s7/img2-1.jpg')"
              alt
            />
            <div class="block-title">業績實景</div>
          </div>
        </div>
        <div class="content-t">
          <div
            class="title"
            data-aos="fade-right"
            data-aos-delay="500"
          >
            家的延伸<br />翻轉想像無限可能
          </div>
        </div>
        <img
          v-lazy="require('./s7/img3-1.jpg')"
          alt
          class="bg-img bottom"
        />
        <img
          v-lazy="require('./s7/box2.png')"
          alt
          class="bg-img bottom"
        />
        <div
          class="content"
          data-aos="fade-left"
          data-aos-delay="500"
        >
          <div class="title">動靜皆宜 交誼廳、吧檯多功用途</div>
          <div class="desc">在家登入放鬆時區，親友相聚、遠迎賓客不必出門，在家就有不失面子的交流空間，有簡易的烹飪區規劃，並擁大面落地窗引入中庭綠意，同時也能是一人靜思小酌的小天地，在溫徐燈光的照拂下，釋放壓力，恣意歡笑。</div>
        </div>
      </div>
      <div v-else>
        <swiper
          :options="swiperOption"
          ref="mySwiper"
          data-aos="fade"
          data-aos-delay="200"
          class="swiper-m"
          @slideChangeTransitionEnd="slideChanged"
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
        <img
          v-lazy="require('./mo/7/title.jpg')"
          alt
          class="img"
        />
        <img
          v-lazy="require('./mo/7/img2-1.jpg')"
          alt
          class="img"
          data-aos="fade"
          data-aos-delay="300"
        />
        <img
          v-lazy="require('./mo/7/img3-1.jpg')"
          alt
          class="img"
          data-aos="fade"
          data-aos-delay="300"
        />
        <div class="relative">
          <img
            v-lazy="require('./mo/7/bg2.png')"
            alt
            class="img"
          />
          <div
            class="content"
            data-aos="fade-left"
            data-aos-delay="500"
          >
            <div class="title">動靜皆宜 交誼廳、吧檯多功用途</div>
            <div class="desc">在家登入放鬆時區，親友相聚、遠迎賓客不必出門，在家就有不失面子的交流空間，有簡易的烹飪區規劃，並擁大面落地窗引入中庭綠意，同時也能是一人靜思小酌的小天地，在溫徐燈光的照拂下，釋放壓力，恣意歡笑。</div>
          </div>
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
  height: size(2275);
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
  z-index: 1;

  &.fix {
    position: fixed;
  }

  &:nth-child(1) {
    position: relative;
  }

  &.bottom {
    top: size(1141);
  }
}

.block-img {
  position: absolute;
  z-index: 3;

  img {
    width: 100%;
  }
}

.block-img-1 {
  width: size(810);
  top: 0;
  right: size(810);
}

.block-img-2 {
  width: size(810);
  top: 0;
  right: 0;
}

.block-img-3 {
  width: size(1740);
  left: 0;
  top: size(682);
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

.content-t {
  position: absolute;
  width: size(320);
  top: size(513);
  left: size(335);
  z-index: 2;
}

.content {
  position: absolute;
  width: size(670);
  bottom: size(780);
  right: size(156);
  z-index: 2;
}

.title {
  font-size: size(40);
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #000000;
  margin-bottom: size(10);
}

.desc {
  font-size: size(16);
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 2.25;
  letter-spacing: normal;
  text-align: left;
  color: #666666;
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
    height: auto;
    display: block;

    img {
      display: block;
    }

    > div {
      display: block;
    }
  }

  .swiper-m {
    width: 100vw;

    .item-img {
      width: 100%;
    }
  }

  .bg-img {
    width: 100vw;
    position: absolute;
    top: auto;
    left: 0;
    bottom: 0;
    height: auto;
    display: block;
    object-fit: cover;
    z-index: 3;

    // &:nth-child(1) {
    //   position: relative;
    // }
  }

  .img {
    width: 100vw;
    position: relative;
  }

  .content {
    width: size-m(300);
    margin: 0 auto;
    top: size-m(50);
  }

  .title {
    font-size: size-m(20);
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
import slider from '@/mixins/slider.js'
import 'swiper/dist/css/swiper.css'

import { swiper, swiperSlide } from 'vue-awesome-swiper'

export default {
  name: 'section7',
  mixins: [slider],
  components: {
    swiper,
    swiperSlide,
  },

  data() {
    return {
      isMobile,
      isTablet,
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
          img: require('./mo/7/img1-1.jpg'),
        },
        {
          img: require('./mo/7/img1-2.jpg'),
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
