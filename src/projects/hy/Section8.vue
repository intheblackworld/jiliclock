<template>
  <div class="section8">
    <div class="bg">
      <div v-if="!isMobile">
        <swiper :options="swiperOption" ref="mySwiper" @slideChangeTransitionEnd="slideChanged">
          <img src="./s8/bg.png" alt class="bg-img" />
          <img src="./s8/top.png" alt class="bg-img" />
          <swiper-slide
            v-for="(slide, index) in slideList"
            :index="index"
            :key="slide.img"
            class="item"
          >
            <img :src="slide.img" :class="`item-img`" />
          </swiper-slide>
          <div :class="`item-content`">
            <div class="item-title">
              {{slideList[slideIndex].title}}
              <!-- <img v-if="isHide" src="./s8/mo/箭頭上.png" alt class="btn" />
              <img v-else src="./s8/mo/箭頭下.png" alt class="btn" /> -->
            </div>
            <div class="item-desc">{{slideList[slideIndex].desc}}</div>
          </div>
          <div class="swiper-button-prev" slot="button-prev">
            <img src="./arrow-left.png" alt />
          </div>
          <div class="swiper-button-next" slot="button-next">
            <img src="./arrow-right.png" alt />
          </div>
        </swiper>
        <div class="content" data-aos="fade-right" data-aos-delay="200">
          <div class="title">
            名宅公設手筆
            <br />滿足心之所嚮
          </div>
          <div class="desc">
            新鮮愉悅的感官體驗，心所嚮往的生活型態
            <br />即興展演出每日的豐盈時光
          </div>
        </div>
      </div>
      <div v-else>
        <swiper :options="swiperOption" ref="mySwiper" @slideChangeTransitionEnd="slideChanged">
          <img src="./s8/mo/box.png" alt class="bg-img" />
          <swiper-slide
            v-for="(slide, index) in slideList"
            :index="index"
            :key="slide.img"
            class="item"
          >
            <img :src="slide.img" :class="`item-img`" />
          </swiper-slide>
          <div :class="`item-content`">
            <div class="item-title">
              <!-- <img v-if="isHide" src="./s8/mo/箭頭上.png" alt class="btn" />
              <img v-else src="./s8/mo/箭頭下.png" alt class="btn" /> -->
              {{slideList[slideIndex].title}}
            </div>
            <div class="item-desc">{{slideList[slideIndex].desc}}</div>
          </div>
          <div class="swiper-button-prev" slot="button-prev">
            <img src="./arrow-left.png" alt />
          </div>
          <div class="swiper-button-next" slot="button-next">
            <img src="./arrow-right.png" alt />
          </div>
        </swiper>
        <div class="content" data-aos="fade-down" data-aos-delay="600">
          <div class="title">
            名宅公設手筆
            <br />滿足心之所嚮
          </div>
          <div class="desc">
            新鮮愉悅的感官體驗，心所嚮往的生活型態
            <br />即興展演出每日的豐盈時光
          </div>
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
  z-index: 3;

  // &:nth-child(1) {
  //   position: relative;
  // }
}

.content {
  position: absolute;
  left: calc(100vw * 100 / 1920);
  bottom: calc(100vh * 60 / 940);
  z-index: 5;
}

.title {
  font-size: calc(100vw * 69 / 1920);
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.09;
  letter-spacing: normal;
  text-align: left;
  color: #ffffff;
  margin-bottom: 20px;
}

.desc {
  font-size: calc(100vw * 25.5 / 1920);
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.47;
  letter-spacing: normal;
  text-align: left;
  color: #ffffff;
}

.item-img {
  &:nth-child(1) {
    position: relative;
  }
  width: 100vw;
  position: absolute;
  display: block;
}

.item-content {
  position: absolute;
  width: calc(100vw * 720 / 1920);
  right: calc(100vw * 100 / 1920);
  bottom: calc(100vh * 64 / 940);
  z-index: 5;
  text-shadow: 0 0 5px #000;
  transition: all 0.3s;

  &.hide {
    bottom: calc(100vh * -30 / 940);

    .item-desc {
      opacity: 0;
    }
  }

  .btn {
    margin-left: 30px;
    width: calc(100vw * 50 / 1920);
    // cursor: pointer;
  }
}

.item-title {
  font-size: calc(100vw * 50 / 1920);
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.09;
  letter-spacing: normal;
  text-align: left;
  color: #ffffff;
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  // cursor: pointer;
}

.item-desc {
  font-size: calc(100vw * 25.5 / 1920);
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.47;
  letter-spacing: normal;
  text-align: left;
  color: #ffffff;
  height: calc(100vh * 64 / 940);
  transition: all 0.3s;
}

// .swiper-container {
//   position: relative;
//   z-index: 2;
// }

.swiper-button-prev,
.swiper-container-rtl .swiper-button-next,
.swiper-button-next,
.swiper-container-rtl .swiper-button-prev {
  z-index: 10;
}

.swiper-button-next,.swiper-button-prev {
  animation: arrow  linear 1s alternate infinite;
}
.swiper-button-next {
  animation-delay:1s;
}

@keyframes arrow {
  to {
      -webkit-transform: translateX(8px);
      transform: translateX(8px)
  }
}

@media only screen and (max-width: 1440px) and (min-width: 1025px) {
  .item-content {
    bottom: calc(100vh * 124 / 940);
  }
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
    height: calc(100vw * 1334 / 750);
    background-size: 100%;
  }

  .bg-img {
    position: absolute;
  }

  .swiper-container {
    height: calc(100vw * 1334 / 750);
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
    margin-top: 0px;
  }

  .item-img {
    width: 100vw;
    margin: 0 auto;
  }

  .content {
    position: absolute;
    right: auto;
    left: calc(100vw * 24 / 375);
    top: auto;
    bottom: calc(100vh * 70 / 675);
  }

  .title {
    font-size: calc(100vw * 36 / 375);
    font-weight: bold;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.09;
    letter-spacing: normal;
    text-align: left;
    color: #ffffff;
    margin-bottom: 15px;
  }

  .desc {
    font-size: calc(100vw * 14 / 375);
    font-weight: bold;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.4;
    letter-spacing: normal;
    text-align: left;
    color: #ffffff;
  }

  .item-content {
    position: absolute;
    z-index: 10;
    left: auto;
    right: calc(100vw * 30 / 375);
    width: calc(100vw * 225 / 375);
    top: auto;
    bottom: calc(100vh * 290 / 675);
    transition: all 0.3s;

    &.hide {
      bottom: calc(100vh * 200 / 675);

      .item-desc {
        opacity: 0;
      }
    }

    .btn {
      width: 27px;
      margin-right: 8px;
      // cursor: pointer;
    }
  }

  .item-title {
    font-size: calc(100vw * 23 / 375);
    font-weight: bold;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.09;
    letter-spacing: normal;
    text-align: right;
    color: #ffffff;
    margin-bottom: 15px;
  }

  .item-desc {
    font-size: calc(100vw * 14 / 375);
    max-height: 57px;
    font-weight: bold;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.4;
    letter-spacing: normal;
    text-align: left;
    color: #ffffff;
    opacity: 1;
    transition: all 0.3s;
  }

  .swiper-button-prev,
  .swiper-container-rtl .swiper-button-next {
    left: 2vw;
  }

  .swiper-button-next,
  .swiper-container-rtl .swiper-button-prev {
    right: 2vw;
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
  name: 'section8',
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
        // autoplay: {
        //   delay: 4000,
        //   disableOnInteraction: true,
        // },
        loop: true,
        effect: 'fade',
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
      },
      slideList: [
        {
          img: !isMobile ? require('./s8/1.jpg') : require('./s8/mo/1.jpg'),
          title: '洲際藝術大廳',
          desc:
            '簡約沉穩的色調，以天然石材紋路結合皮革及金屬，設計出獨具品味的氛圍，讓出門回家多了一份沉靜自在',
        },
        {
          img: !isMobile ? require('./s8/2.jpg') : require('./s8/mo/2.jpg'),
          title: '童樂書屋',
          desc:
            '流線型的天花板設計，開啟孩子眼中的奇妙視界；圓潤樸質的仿石椅及溫暖木質，與大片玻璃窗外的自然相互呼應，在遊樂中啟發孩子的大未來',
        },

        {
          img: !isMobile ? require('./s8/3.jpg') : require('./s8/mo/3.jpg'),
          title: '沐光會議室',
          desc:
            '透過落地玻璃，欣賞生趣盎然的綠色窗景和明亮的自然光；開闊的木紋大桌，悅納天馬行空的創意，讓每一次聚首都滿載而歸',
        },
        {
          img: !isMobile ? require('./s8/4.jpg') : require('./s8/mo/4.jpg'),
          title: '花水綠健身房',
          desc:
            '通透的落地大面玻璃，迎來天然光線與景觀，在明亮寬敞的室內空間，以舒適的溫度盡興運動，享受VIP級的健身體驗',
        },
      ],
    }
  },

  methods: {
    slideChanged(e) {
      const swiper = this.$refs.mySwiper.swiper
      console.log(this.slideIndex)
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
