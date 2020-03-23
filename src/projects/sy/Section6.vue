<template>
  <div class="section6">
    <div class="bg">
      <img src="./s6/bg2.png" alt class="bg-img" />
      <div v-if="!isMobile">
        <div class="content">
          <div>
            <div class="title" data-aos="fade-right" data-aos-delay="600">世代第一首選</div>
            <div class="subtitle" data-aos="fade-right" data-aos-delay="700">ONLY ONE CHOICE</div>
            <div class="red-title" data-aos="fade-right" data-aos-delay="800">自住兼置產，富貴興旺代代相傳</div>
            <div
              class="desc"
              data-aos="fade-right" data-aos-delay="900"
            >首購一步到位，首換全面升級！專為獨立成家、二代置產或世代共居的首購換屋族而規劃，新莊第一名宅的「璽園」，兼具自住享受、置產增值，何止是一棟好地段的豪宅，更是一座宜居好宅、世代傳承的建築。</div>
          </div>
        </div>
        <swiper :options="swiperOption" ref="mySwiper" data-aos="fade" data-aos-delay="600">
          <swiper-slide
            v-for="(slide, index) in slideList"
            :index="index"
            :key="slide.img"
            class="item"
          >
            <img :src="slide.src" :class="`item-img`" />
          </swiper-slide>
          <div class="swiper-button-prev" slot="button-prev">
            <img src="./arrow-left.png" alt />
          </div>
          <div class="swiper-button-next" slot="button-next">
            <img src="./arrow-right.png" alt />
          </div>
        </swiper>
      </div>
      <div v-else>
        <div class="content">
          <div class="title" data-aos="fade-right" data-aos-delay="600">世代第一首選</div>
          <div class="subtitle" data-aos="fade-right" data-aos-delay="800">ONLY ONE CHOICE</div>
          <div class="red-title" data-aos="fade-right" data-aos-delay="1000">自住兼置產，富貴興旺代代相傳</div>
          <div
            class="desc"
            data-aos="fade-right" data-aos-delay="1200"
          >首購一步到位，首換全面升級！專為獨立成家、二代置產或世代共居的首購換屋族而規劃，新莊第一名宅的「璽園」，兼具自住享受、置產增值，何止是一棟好地段的豪宅，更是一座宜居好宅、世代傳承的建築。</div>
        </div>
        <swiper :options="swiperOption" ref="mySwiper" data-aos="fade-right" data-aos-delay="1200">
          <swiper-slide
            v-for="(slide, index) in slideList"
            :index="index"
            :key="slide.img"
            class="item"
          >
            <img :src="slide.src" :class="`item-img`" />
          </swiper-slide>
          <div class="swiper-button-prev" slot="button-prev">
            <img src="./arrow-left.png" alt />
          </div>
          <div class="swiper-button-next" slot="button-next">
            <img src="./arrow-right.png" alt />
          </div>
        </swiper>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.bg {
  background-size: 100% 100%;
  background-repeat: no-repeat;
  background-position: bottom;
  position: relative;
  overflow: hidden;
  background-image: url('./s6/bg1.png');

  > div {
    display: flex;
  }
}

.bg-img {
  width: calc(100vw * (640 / 1920));
  height: auto;
  position: absolute;
  bottom: 0;
  left: 0;
  display: block;
}

.item-img {
  &:nth-child(1) {
    position: relative;
  }
  width: 100%;
  position: absolute;
  display: block;
}

.swiper-container {
  width: calc(100vw * 2 / 3);
}

.content {
  width: calc(100vw * 1 / 3);
  padding-left: 0px;
  position: relative;
  z-index: 2;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;

  > div {
    width: 370px;
    max-width: 90vw;
  }
}

.title {
  font-size: calc(100vw * 58 / 1920);
  font-weight: normal;
  font-style: normal;
  font-stretch: normal;
  line-height: 0.66;
  letter-spacing: normal;
  text-align: left;
  color: #507913;
  margin-bottom: calc(100vw * 20 / 1920);
}

.subtitle {
  font-size: calc(100vw * 22 / 1920);
  font-family: 'Abril Fatface', cursive;
  font-weight: normal;
  font-style: normal;
  font-stretch: normal;
  line-height: 1.73;
  letter-spacing: normal;
  text-align: left;
  color: #91b260;
  margin-bottom: calc(100vw * 35 / 1920);
}

.red-title {
  font-size: calc(100vw * 26 / 1920);
  font-weight: normal;
  font-style: normal;
  font-stretch: normal;
  line-height: 1.46;
  letter-spacing: normal;
  text-align: left;
  color: #d67684;
  white-space: nowrap;
  margin-bottom: calc(100vw * 15 / 1920);
}

.desc {
  font-size: calc(100vw * 18 / 1920);
  font-weight: normal;
  font-style: normal;
  font-stretch: normal;
  line-height: 2.11;
  letter-spacing: normal;
  text-align: justify;
  color: #656565;
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
    padding: 40px 0;

    > img {
      display: block;
    }
  }

  .bg-img {
    top: 0;
    bottom: 0;
    height: auto;
  }

  .content > div {
    width: 240px;
  }

  .desc {
    margin-bottom: calc(100vw * 20 / 1920);
  }

  .item-desc {
    width: 400px;
    margin-bottom: calc(100vw * 10 / 1920);
  }
}

@media screen and (max-width: 767px) {
  .bg {
    background-size: 100% 100%;
    background-image: none;
    padding-top: 0;
    padding-bottom: 0;

    > div {
      display: block;
    }
  }

  .title {
    font-size: 39.5px;
    font-weight: normal;
    font-style: normal;
    font-stretch: normal;
    line-height: 0.66;
    letter-spacing: normal;
    text-align: left;
    color: #507913;
    margin-bottom: 10px;
  }

  .subtitle {
    font-size: 15px;
    font-weight: normal;
    font-style: normal;
    font-stretch: normal;
    line-height: 1.73;
    letter-spacing: normal;
    text-align: left;
    color: #91b260;
    margin-bottom: 20px;
  }

  .red-title {
    font-size: 17.5px;
    font-weight: normal;
    font-style: normal;
    font-stretch: normal;
    line-height: 1.49;
    letter-spacing: normal;
    text-align: left;
    color: #d67684;
  }

  .desc {
    font-size: 15px;
    font-weight: normal;
    font-style: normal;
    font-stretch: normal;
    line-height: 1.67;
    letter-spacing: normal;
    text-align: justify;
    color: #656565;
  }

  .swiper-container {
    width: 100vw;
    margin-top: 5px;
  }

  .content {
    width: 100vw;
    background-image: url('./mobg.jpg');
    background-size: cover;
    padding: 50px 20px 45px;
  }

  .item-img {
    &:nth-child(1) {
      position: relative;
    }
    width: 100vw;
    position: absolute;
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
        // effect: 'fade',
        loop: true,
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
      },
      slideList: [
        {
          src: require('./s6/PP_02317.jpg'),
        },
        {
          src: require('./s6/PP_02310.jpg'),
        },

        {
          src: require('./s6/PP_02243.jpg'),
        },
        {
          src: require('./s6/PP_02238.jpg'),
        },
        {
          src: require('./s6/PP_02217.jpg'),
        },
        {
          src: require('./s6/PP_02210.jpg'),
        },
        {
          src: require('./s6/PP_02169.jpg'),
        },
        {
          src: require('./s6/PP_02148.jpg'),
        },
      ],
    }
  },

  methods: {},
}
</script>
