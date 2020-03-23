<template>
  <div class="section8">
    <div class="bg">
      <div v-if="!isMobile">
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
        <img src="./s8/bg.png" alt="" class="bg-img">
        <div class="content">
          <img :src="slideList[slideIndex].desc" :alt="slideList[slideIndex].alt" :class="`bg-img`" />
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
  top: 0;
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
      white-space: nowrap;
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
      height: 250px;
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
  name: 'section8',
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
          img: isMobile
            ? require('./s8/mo/s8-1.jpg')
            : require('./s8/s7-1.png'),
          title: '謙隱 「美術館」特區<br />人文藝術無價',
          desc: isMobile
            ? '【堅山謙仰】謙居高雄「美術館特區」優質地段，與南台灣最重量級、最具品味的「美術館」當鄰居，美術館、兒童美術館與41公頃自然生態豐富的「內惟埤文化園區」，藝術、文化、創意、 生態、教育的底蘊豐厚之地，國際與國內重要藝術風潮、藝術家、作品…精彩展出。地段價值無可衡量，是您一生難得的無價傳承。'
            : require('./s8/s7-1t.png'),
          alt: '精鑄原創圖騰',
        },
        {
          img: isMobile
            ? require('./s8/mo/s8-2.jpg')
            : require('./s8/s7-2.png'),
          title: '森藏「馬卡道路」<br />百米綠廊道',
          desc: isMobile
            ? '高雄啟動鐵路地下化工程，串聯更完善便利的交通網絡，上方土地將啟動景觀園道規劃，打造綠廊、水廊、自行車道及寬敞人行空間。<br /><br />【堅山謙仰】鄰近捷運輕軌C20站，門外馬卡道路百米綠廊道，將遍植紅花風鈴木、阿勃勒、黃花風鈴木、鐵刀木…等景觀喬木，成為您森活的窗景，漫步的風景。'
            : require('./s8/s7-2t.png'),
          alt: '打造退縮頂冠',
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
