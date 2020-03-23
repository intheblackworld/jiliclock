<template>
  <div class="section4">
    <div class="bg">
      <img src="./s4/bg1.png" alt class="bg-img" />
      <div v-if="!isMobile">
        <div class="content">
          <div>
            <div class="title" data-aos="fade-right" data-aos-delay="600">豪宅精品美學</div>
            <div class="subtitle" data-aos="fade-right" data-aos-delay="700">HIGH STANDARDS</div>
            <div class="red-title" data-aos="fade-right" data-aos-delay="800">摩登亞洲風成就精品飯店宅</div>
            <div class="desc" data-aos="fade-right" data-aos-delay="900">國際級飯店規格，挑高6米氣派門廳，規劃閱覽休憩區、時尚視聽室、交誼沙龍區到空中宴會區等，回家就像回飯店。</div>
          </div>
        </div>
        <swiper :options="swiperOption" ref="mySwiper" data-aos="fade-left" data-aos-delay="600">
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
          <div class="title" data-aos="fade-right" data-aos-delay="600">豪宅精品美學</div>
          <div class="subtitle" data-aos="fade-right" data-aos-delay="800">HIGH STANDARDS</div>
          <div class="red-title" data-aos="fade-right" data-aos-delay="1000">摩登亞洲風成就精品飯店宅</div>
          <div class="desc" data-aos="fade-right" data-aos-delay="1200">國際級飯店規格，挑高6米氣派門廳，規劃閱覽休憩區、時尚視聽室、交誼沙龍區到空中宴會區等，回家就像回飯店。</div>
        </div>
        <swiper :options="swiperOption" ref="mySwiper" data-aos="fade" data-aos-delay="1000">
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
  background-size: 100% 70%;
  background-repeat: no-repeat;
  background-position: bottom;
  position: relative;
  overflow: hidden;
  background-image: url('./s4/bg2.png');

  > div {
    display: flex;
  }
}

.bg-img {
  width: 100vw;
  height: auto;
  position: absolute;
  height: auto;
  display: block;
  top: 0;
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
        // effect: 'fade',
        loop: true,
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
      },
      slideList: [
        {
          src: require('./s4/1.jpg'),
        },
        {
          src: require('./s4/2.jpg'),
        },

        {
          src: require('./s4/3.jpg'),
        },
        {
          src: require('./s4/4.jpg'),
        },
        {
          src: require('./s4/5.jpg'),
        },
        {
          src: require('./s4/6.jpg'),
        },
        {
          src: require('./s4/7.jpg'),
        },
        {
          src: require('./s4/8.jpg'),
        },
        {
          src: require('./s4/9.jpg'),
        },
        {
          src: require('./s4/10.jpg'),
        },
        {
          src: require('./s4/11.jpg'),
        },
      ],
    }
  },

  methods: {
  },
}
</script>
