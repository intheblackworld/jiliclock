<template>
  <div class="section6">
    <div class="bg">
      <div v-if="!isMobile">
        <img src="./s6/title.png" alt="感動 從分享生活的美好開始" class="bg-img" data-aos="fade-down" data-aos-delay="600" />
        <swiper :options="swiperOption" ref="mySwiper" data-aos="fade-down" data-aos-delay="800">
          <swiper-slide
            v-for="(slide, index) in slideList"
            :index="index"
            :key="slide.img"
            class="item"
          >
            <img :src="slide.img" :class="`item-img`" />
            <!-- <img src="./s6/1.png" alt :class="`bg-img`" />
            <img
              src="./s6/2.png"
              alt="站在規劃者的角度，在建築落成後導入歐洲貴族沙龍文化精神，透過公共空間籌備沙龍藝術季—舉辦國際畫展、拍賣會、品酒會… 等精彩活動，希望建築可以傳遞與分享美好生活美學。"
              :class="`bg-img`"
            /> -->
          </swiper-slide>
          <div class="swiper-button-prev" slot="button-prev">
            <img src="./arrow-left.png" alt />
          </div>
          <div class="swiper-button-next" slot="button-next">
            <img src="./arrow-right.png" alt />
          </div>
        </swiper>
        <div class="content">
          <img src="./s6/1.png" alt :class="`bg-img`" />
          <img
            src="./s6/2.png"
            alt="站在規劃者的角度，在建築落成後導入歐洲貴族沙龍文化精神，透過公共空間籌備沙龍藝術季—舉辦國際畫展、拍賣會、品酒會… 等精彩活動，希望建築可以傳遞與分享美好生活美學。"
            :class="`bg-img`"
            data-aos="fade-down" data-aos-delay="1000"
          />
        </div>
      </div>
      <div v-else>
        <img src="./s6/mo/title.png" alt="感動 從分享生活的美好開始" class="bg-img" />
        <swiper :options="swiperOption" ref="mySwiper" @slideChangeTransitionEnd="slideChanged">
          <swiper-slide
            v-for="(slide, index) in slideList"
            :index="index"
            :key="slide.img"
            class="item"
          >
            <img :src="slide.img" :class="`item-img`" />
          </swiper-slide>
          <div class="swiper-button-prev" slot="button-prev">
            <img src="./arrow-left.png" alt />
          </div>
          <div class="swiper-button-next" slot="button-next">
            <img src="./arrow-right.png" alt />
          </div>
        </swiper>
        <div class="text">
          <div
            class="desc"
          >站在規劃者的角度，在建築落成後導入歐洲貴族沙龍文化精神，透過公共空間籌備沙龍藝術季—舉辦國際畫展、拍賣會、品酒會… 等精彩活動，希望建築可以傳遞與分享美好生活美學。</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.bg {
  background-size: cover;
  position: relative;
  overflow: hidden;
  position: relative;
}

.bg-img {
  width: 100vw;
  position: absolute;
  top: 0;
  left: 0;
  height: auto;
  display: block;
  object-fit: cover;

  &:nth-child(1) {
    position: relative;
  }
}

.content {
  position: absolute;
  z-index: 0;
  top: calc(100vw * (400 / 1920));
}

.item-img {
  &:nth-child(1) {
    position: relative;
  }
  width: 100vw;
  position: absolute;
}

// .swiper-container {
//   z-index: 2;
// }

// .swiper-button-prev, .swiper-container-rtl .swiper-button-next, .swiper-button-next, .swiper-container-rtl .swiper-button-prev {
//   z-index: 10;
// }

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
    width: 100vw;
    background-size: 100%;
  }

  .text {
    padding-top: 52px;
    padding-bottom: 70px;
    background-image: url('./s6/mo/bg.jpg');
    background-size: 100%;
    background-position: 100% 100%;
    margin-top: -3px;

    .title {
      width: 275px;
      font-size: 25px;
      font-weight: 600;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.4;
      letter-spacing: 2.5px;
      text-align: left;
      color: #000000;
      margin: 0 auto;
      margin-bottom: 27px;
    }

    .desc {
      width: 283px;
      font-size: 14px;
      font-weight: 300;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.7;
      letter-spacing: 1.5px;
      text-align: left;
      color: #fff;
      margin: 0 auto;
    }
  }

  .swiper-container {
    margin-top: 30px;
  }

  .item-img {
    width: 100vw;
    margin: 0 auto;
  }

  .swiper-button-prev,
  .swiper-container-rtl .swiper-button-next {
    // left: 5vw;
  }

  .swiper-button-next,
  .swiper-container-rtl .swiper-button-prev {
    // right: 5vw;
  }

  .img {
    width: 100vw;
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
  name: 'section6',
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
        effect: 'fade',
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
      },
      slideList: [
        {
          img: isMobile
            ? require('./s6/mo/s6-1.jpg')
            : require('./s6/s6-1.png'),
        },
        {
          img: isMobile
            ? require('./s6/mo/s6-2.jpg')
            : require('./s6/s6-2.png'),
        },

        // {
        //   img: isMobile
        //     ? require('./s6/mo/s6-3.jpg')
        //     : require('./s6/s6-3.png'),
        // },
        // {
        //   img: isMobile
        //     ? require('./s6/mo/s6-4.jpg')
        //     : require('./s6/s6-4.png'),
        // },
        {
          img: isMobile
            ? require('./s6/mo/s6-5.jpg')
            : require('./s6/s6-5.png'),
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
