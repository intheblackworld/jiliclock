<template>
  <div class="section4">
    <div class="bg">
      <div v-if="!isMobile">
        <img src="./s4/title.png" alt="堅持無數細節 詮釋ART DECO之美" class="bg-img" />
        <swiper
          :options="swiperOption"
          ref="mySwiper"
          data-aos="fade-down"
          data-aos-delay="800"
          @slideChangeTransitionEnd="slideChanged"
        >
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
        <div class="content">
          <img :src="slideList[slideIndex].desc" :alt="slideList[slideIndex].alt" :class="`bg-img`" />
        </div>
        <div class="relative">
          <img src="./s4/d0.png" alt class="bg-img" />
          <img src="./s4/d1.png" alt class="bg-img" />
        </div>
      </div>
      <div v-else>
        <img src="./s4/mo/title.png" alt="堅持無數細節 詮釋ART DECO之美" class="bg-img" />
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
          <h3 class="title">{{slideList[slideIndex].title}}</h3>
          <div class="desc">{{slideList[slideIndex].desc}}</div>
        </div>
        <img src="./s4/mo/2.jpg" alt class="img" />
        <img src="./s4/mo/3.jpg" alt class="img" />
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

.item-img {
  &:nth-child(1) {
    position: relative;
  }
  width: 100vw;
  position: absolute;
}

.content {
  position: absolute;
  z-index: 0;
  top: calc(100vw * (400 / 1920));
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
      height: 70px;
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
  name: 'section4',
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
        effect: 'fade',
        loop: true,
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
      },
      slideList: [
        {
          img: isMobile ? require('./s4/mo/c1.jpg') : require('./s4/c1.png'),
          title: '精鑄原創圖騰',
          desc: isMobile
            ? '在入口地面與建築體原創噴泉與山的變形圖騰，做為家族特色家徽，展現綻放曙光的精神。'
            : require('./s4/c1t.png'),
          alt: '精鑄原創圖騰',
        },
        {
          img: isMobile ? require('./s4/mo/c2.jpg') : require('./s4/c2.png'),
          title: '打造退縮頂冠',
          desc: isMobile
            ? '頂樓處以退縮設計形成特色屋突，打造可遠眺壽山、愛河與美術館的休憩空間。'
            : require('./s4/c2t.png'),
          alt: '打造退縮頂冠',
        },

        {
          img: isMobile ? require('./s4/mo/c3.jpg') : require('./s4/c3.png'),
          title: '建築的力與美',
          desc: isMobile
            ? '一、二樓天然石材基座，搭配正面大型金屬鐵件裝置藝術搭配金屬造型燈柱，展現建築力量與壯闊氣勢！'
            : require('./s4/c3t.png'),
          alt: '建築的力與美',
        },
        {
          img: isMobile ? require('./s4/mo/c4.jpg') : require('./s4/c4.png'),
          title: '摩登幾何圖形',
          desc: isMobile
            ? '在建築外觀與室內空間巧思設計常見幾何圖型的變化意象，展現摩登時代感。'
            : require('./s4/c4t.png'),
          alt: '摩登幾何圖形',
        },
        {
          img: isMobile ? require('./s4/mo/c5.jpg') : require('./s4/c5.png'),
          title: '華麗低調質感',
          desc: isMobile
            ? '外觀以金色與米色為主色調，搭配金屬構件，公共場域與傢俱家飾則以紅、金、古銅…展現ARTDECO低調奢華感。'
            : require('./s4/c5t.png'),
          alt: '華麗低調質感',
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
