<template>
  <div class="section5">
    <div class="bg">
      <div v-if="!isMobile" class="d-flex">
        <div class="item" data-aos="fade-down" data-aos-delay="600">
          <img src="./s5/1.jpg" alt class="img" />
          <div class="mask">
            <h3 class="title">1F交誼廳</h3>
            <div class="desc">
              映入眼簾的是穿透延伸出去的雕塑及充滿藝術圖的鍍鈦屏風，在無盡的空間裡面添加更多的視覺藝術，而義大利百年的Poltrana Frau家具的多樣性及頂級觸感，將整個入口感覺點妝成為不可取代的雅痞空間，透過屏風背後精緻的吧檯設計及長形用餐桌面，提供了一個夜晚繁星休憩的美食饗宴空間。
            </div>
          </div>
        </div>
        <div class="item" data-aos="fade-left" data-aos-delay="800">
          <img src="./s5/2.jpg" alt class="img" />
          <div class="mask">
            <h3 class="title">2F健身空間</h3>
            <div class="desc">
              在廊道上利用煙燻的刻紋木皮，讓整個走廊散發出軟性的效果，進入到室內空間，環形設計的天花板成為整個空間的視覺主軸，整個空間的設計圍繞在環形架構上，搭配間接照明設計，讓健身同時享受著不單調的趣味性。
            </div>
          </div>
        </div>
        <div class="item" data-aos="fade-up" data-aos-delay="1000">
          <img src="./s5/3.jpg" alt class="img" />
          <div class="mask">
            <h3 class="title">14F的視聽會所</h3>
            <div class="desc">
              交錯分隔的天花板造型，搭配圖騰義大利灰石材的協面分割，就像在畫作上的線條與色塊的結合，藝術的價值與空間美感，相互呼應會所，就是一個私人典藏的空間，身在其中如同一個頂級奢華的俱樂部，盡情抒發內心的熱情。
            </div>
          </div>
        </div>
      </div>
      <div v-else>
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
          <h3 class="title" v-html="slideList[slideIndex].title"></h3>
          <div class="desc" v-html="slideList[slideIndex].desc"></div>
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

.item {
  width: calc(100vw / 3);
  position: relative;

  .img {
    width: 100%;
    height: auto;
    object-fit: cover;
    display: block;
  }

  .mask {
    background: rgba(0, 0, 0, 0.7);
    opacity: 0;
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    z-index: 2;
    transition: all 0.4s;
    padding: 60px 50px 0 50px;
  }

  &:hover {
    .mask {
      opacity: 1;
    }
  }

  .title {
    font-size: calc(100vw * (30 / 1920));
    font-weight: 600;
    font-style: normal;
    font-stretch: normal;
    line-height: 1.33;
    letter-spacing: 3px;
    text-align: left;
    color: #ffffff;
    margin-bottom: 20px;
  }

  .desc {
    font-size: calc(100vw * (18 / 1920));
    font-weight: normal;
    font-style: normal;
    font-stretch: normal;
    line-height: 2.22;
    letter-spacing: 1.8px;
    text-align: justify;
    color: #ffffff;
  }
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

  .item {
    .mask {
      padding: 20px 20px;

      .title {
        margin-bottom: 5px;
        font-size: 18px;
      }

      .desc {
        font-size: 12px;
        line-height: 1.7;
      }
    }
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
      width: 275px;
      font-size: 14px;
      font-weight: 300;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.71;
      letter-spacing: 1.5px;
      text-align: justify;
      color: #000000;
      margin: 0 auto;
      margin-bottom: 70px;
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
  name: 'section5',
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
        // autoplay: {
        //   delay: 4000,
        //   disableOnInteraction: true,
        // },
        loop: true,
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
      },
      slideList: [
        {
          img: require('./s5/mo/1.jpg'),
          title: '1F交誼廳',
          desc:
            '映入眼簾的是穿透延伸出去的雕塑及充滿藝術圖的鍍鈦屏風，在無盡的空間裡面添加更多的視覺藝術，而義大利百年的Poltrana Frau家具的多樣性及頂級觸感，將整個入口感覺點妝成為不可取代的雅痞空間，透過屏風背後精緻的吧檯設計及長形用餐桌面，提供了一個夜晚繁星休憩的美食饗宴空間。',
        },
        {
          img: require('./s5/mo/2.jpg'),
          title: '2F健身空間',
          desc:
            '在廊道上利用煙燻的刻紋木皮，讓整個走廊散發出軟性的效果，進入到室內空間，環形設計的天花板成為整個空間的視覺主軸，整個空間的設計圍繞在環形架構上，搭配間接照明設計，讓健身同時享受著不單調的趣味性。',
        },

        {
          img: require('./s5/mo/3.jpg'),
          title: '14F的視聽會所',
          desc:
            '交錯分隔的天花板造型，搭配圖騰義大利灰石材的協面分割，就像在畫作上的線條與色塊的結合，藝術的價值與空間美感，相互呼應會所，就是一個私人典藏的空間，身在其中如同一個頂級奢華的俱樂部，盡情抒發內心的熱情。',
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
