<template>
  <div class="section7">
    <div class="bg">
      <div v-if="!isMobile">
        <img src="./s7/t1.png" alt="安全高規格 日本住友制震壁" class="bg-img" data-aos="fade-down" data-aos-delay="600" />
        <img src="./s7/t2.png" alt="新莊第一名宅 在地唯一指名" class="bg-img" data-aos="fade-down" data-aos-delay="800" />
        <img src="./s7/t3.png" alt="新莊市中心，最後一塊千坪美地" class="bg-img" data-aos="fade-down" data-aos-delay="1000" />
        <img src="./s7/t4.png" alt="地標飯店宅 29坪．45坪．52坪" class="bg-img" data-aos="fade-down" data-aos-delay="1200" />
        <div :class="`slide relative`" data-aos="fade" data-aos-delay="0">
          <img
            v-for="(slide, index) in slideList"
            :class="`slide-img ${slideIndex === index ? 'active' : ''}`"
            :key="`s7-slide-${index}`"
            :src="slide.src"
            alt
          />
        </div>
      </div>
      <div v-else>
        <img src="./s7/s7t1.png" alt="安全高規格 日本住友制震壁" class="bg-img" data-aos="fade-down" data-aos-delay="600" />
        <img src="./s7/s7t2.png" alt="新莊第一名宅 在地唯一指名" class="bg-img" data-aos="fade-down" data-aos-delay="800" />
        <img src="./s7/s7t3.png" alt="新莊市中心，最後一塊千坪美地" class="bg-img" data-aos="fade-down" data-aos-delay="1000" />
        <img src="./s7/s7t4.png" alt="地標飯店宅 29坪．45坪．52坪" class="bg-img" data-aos="fade-down" data-aos-delay="1200" />
        <div :class="`slide relative`" data-aos="fade" data-aos-delay="0">
          <img
            v-for="(slide, index) in slideList"
            :class="`slide-img ${slideIndex === index ? 'active' : ''}`"
            :key="`s7-slide-${index}`"
            :src="slide.src"
            alt
          />
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
  margin-top: -1px;
  margin-left: -1px;
}

.bg-img {
  width: 100vw;
  position: absolute;
  top: 0;
  left: 0;
  height: auto;
  display: block;
  object-fit: cover;
  z-index: 5;

  // &:nth-child(1) {
  //   position: relative;
  // }
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
    margin-top: 52px;

    .title {
      width: 283px;
      font-size: 25px;
      font-weight: 600;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.4;
      letter-spacing: 2.5px;
      text-align: left;
      color: #000000;
      margin: 0 auto;
      margin-bottom: 34px;
    }

    .desc {
      width: 283px;
      font-size: 14px;
      font-weight: 300;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.71;
      letter-spacing: 1.5px;
      text-align: justify;
      color: #000000;
      margin: 0 auto;
      margin-bottom: 90px;
    }
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

export default {
  name: 'section7',
  mixins: [slider],

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
          delay: 1000,
          disableOnInteraction: false,
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
          src: isMobile ? require('./s7/s7bg1.jpg') : require('./s7/bg1.jpg'),
        },
        {
          src: isMobile ? require('./s7/s7bg2.jpg') : require('./s7/bg2.jpg'),
        },
        {
          src: isMobile ? require('./s7/s7bg3.jpg') : require('./s7/bg3.jpg'),
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
    setInterval(() => {
      if (this.slideList) {
        this.addIndex()
      }
      if (this.slideList1) {
        this.addMultiIndex(1)
      }

      if (this.slideList2) {
        this.addMultiIndex(2)
      }

      if (this.slideList3) {
        this.addMultiIndex(3)
      }

      if (this.slideList4) {
        this.addMultiIndex(4)
      }
    }, 4000)
  },
}
</script>
