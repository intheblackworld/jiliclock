<template>
  <div class="section9">
    <div class="bg">
      <div v-if="!isMobile">
        <img
          v-lazy="require('./s9/bg.png')"
          alt
          class="bg-img"
        />
        <img
          v-lazy="require('./s9/1.jpg')"
          alt
          class="img-t"
        />
        <div
          class="swiper-button-prev"
          slot="button-prev"
        >
          <img
            src="./all/箭頭2.png"
            alt
          />
        </div>
        <div
          class="swiper-button-next"
          slot="button-next"
        >
          <img
            src="./all/箭頭1.png"
            alt
          />
        </div>
        <div class="content-t">
          <div class="title">職人工藝 品質至上</div>
          <div class="desc">京城建設的建築工法，皆經過建築師與構技師專業的計算評估，堅持按圖施工，嚴格落實鋼筋數量、鋼筋數號，確實做到鋼筋綁紮、混凝土密度強度，以確保建物安全穩固。</div>
        </div>
        <div class="container"></div>
        <swiper
          :options="swiperOption"
          ref="mySwiper"
          data-aos="fade"
          data-aos-delay="200"
          class="swiper-l"
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
            <div
              class="item-title"
              v-html="slide.name"
            ></div>
          </swiper-slide>
        </swiper>
        <transition-group
          name="slide-fade"
          mode="out-in"
        >
          <div
            class="content"
            v-for="(slide, index) in slideList"
            v-show="index === slideIndex"
            :key="slide.img"
          >
            <div
              class="title"
              v-html="slideList[slideIndex].title"
            ></div>
            <div
              class="desc"
              v-html="slideList[slideIndex].desc"
            ></div>
          </div>
        </transition-group>
      </div>
      <div v-else>
        <img
          v-lazy="require('./mo/9/bg.png')"
          alt
          class="bg-img"
        />
        <img
          v-lazy="require('./mo/9/bg2.png')"
          alt
          class="bg-img fix"
        />
        <img
          v-lazy="require('./mo/9/1.png')"
          alt
          class="bg-img"
          data-aos="fade"
          data-aos-delay="300"
        />
        <div class="content-t">
          <div class="title">職人工藝 品質至上</div>
          <div class="desc">京城建設的建築工法，皆經過建築師與構技師專業的計算評估，堅持按圖施工，嚴格落實鋼筋數量、鋼筋數號，確實做到鋼筋綁紮、混凝土密度強度，以確保建物安全穩固。</div>
        </div>
        <swiper
          :options="swiperOption"
          ref="mySwiper"
          data-aos="fade"
          data-aos-delay="200"
          class="swiper-l"
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
            <div
              class="item-title"
              v-html="slide.name"
            ></div>
          </swiper-slide>
        </swiper>
        <transition-group
          name="slide-fade"
          mode="out-in"
        >
          <div
            class="content"
            v-for="(slide, index) in slideList"
            v-show="index === slideIndex"
            :key="slide.img"
          >
            <div
              class="title"
              v-html="slideList[slideIndex].title"
            ></div>
            <div
              class="desc"
              v-html="slideList[slideIndex].desc"
            ></div>
          </div>
        </transition-group>
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
  height: size(1226);
}
.swiper-button-prev,
.swiper-button-next {
  top: 63%;
}
.bg-img {
  width: 100vw;
  position: absolute;
  top: 0;
  left: 0;
  height: auto;
  display: block;
  object-fit: cover;
  z-index: 0;

  &:nth-child(1) {
    // position: relative;
  }
}

.img-t {
  width: size(865);
  top: size(85);
  left: 0;
  position: absolute;
}

.content-t {
  width: size(716);
  top: size(139);
  right: size(244);
  position: absolute;
  .title {
    font-size: size(40);
    font-weight: bold;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.5;
    letter-spacing: normal;
    text-align: left;
    color: #ffffff;
    margin-bottom: size(20);
  }

  .desc {
    font-size: size(16);
    font-weight: normal;
    font-stretch: normal;
    font-style: normal;
    line-height: 2.25;
    letter-spacing: normal;
    text-align: left;
    color: #ffffff;
  }
}

.container {
  width: size(1550);
  height: size(730);
  z-index: 1;
  left: 0;
  right: 0;
  margin: 0 auto;
  top: size(419);
  position: absolute;
  background-color: #fff;
}

.content {
  width: size(620);
  z-index: 3;
  top: size(690);
  right: size(275);
  position: absolute;
}

.title {
  font-size: size(40);
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.48;
  letter-spacing: normal;
  text-align: left;
  color: #20969b;
  margin-bottom: calc(100vw * 15 / 1920);
}

.desc {
  font-size: size(16);
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 2.25;
  letter-spacing: normal;
  text-align: left;
  color: #000000;
}

.swiper-l {
  width: size(775);
  left: size(185);
  bottom: size(77);
  position: absolute;
}

.item-img {
  width: 100%;
  height: auto;
}

.item-title {
  font-size: calc(100vw * 16 / 1920);
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

// begin
.slide-fade-leave-to
/* .slide-fade-leave-active for below version 2.1.8 */ {
  // margin-top: 50px !important;
  opacity: 0;
}
// end
.slide-fade-enter {
  margin-top: 10px !important;
  opacity: 0;
}

.slide-fade-enter-active {
  transition: all 0.5s ease;
}

.slide-fade-leave-active {
  transition: all 0s cubic-bezier(1, 0.5, 0.8, 1);
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

    > img {
      display: block;
    }

    > div {
      display: block;
    }
  }

  .bg-img {
    width: 100vw;
    position: absolute;
    top: 0;
    left: 0;
    bottom: auto;
    height: auto;
    display: block;
    object-fit: cover;
    z-index: 1;

    &.fix {
      position: fixed;
    }

    &:nth-child(1) {
      position: relative;
    }
  }

  .content-t {
    width: size-m(295);
    left: 0;
    right: 0;
    margin: 0 auto;
    top: size-m(263);
    z-index: 3;
    .title {
      width: 100%;
      font-size: size-m(22);
    }

    .desc {
      width: 100%;
      font-size: size-m(12);
    }
  }

  .title-logo {
    width: 100vw;
    z-index: 10;
  }

  .title {
    font-size: calc(100vw * 29 / 375);
    width: 90vw;
    margin: 0 auto;
    font-weight: bold;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.48;
    letter-spacing: 2.32px;
    text-align: left;
    color: #ffffff;
    margin-top: calc(100vw * 45 / 375);
    margin-bottom: calc(100vw * 17 / 375);
  }

  .desc {
    font-size: calc(100vw * 12 / 375);
    width: 90vw;
    margin: 0 auto;
    font-weight: normal;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.58;
    letter-spacing: 0.48px;
    text-align: left;
    color: #cccccc;
    padding-bottom: 31vw;
  }

  .swiper-l {
    width: 200vw;
    left: -50vw;
    top: size-m(516);
    right: 0;
    z-index: 3;

    .item-img {
      // width: size-m(220);
    }
  }

  .content {
    width: size-m(320);
    top: size-m(756);
    left: size-m(31);
    right: 0;
  }

  .title {
    font-size: size-m(20);
    color: #2a8e93;
    width: 100%;
  }

  .desc {
    font-size: size-m(12);
    color: #070303;
    width: 100%;
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
  name: 'section9',
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
        slidesPerView: isMobile ? 3 : 1,
        spaceBetween: isTablet ? 10 : 30,
        slidesPerColumn: isMobile ? 1 : 1,
        allowSlidePrev: isMobile ? true : true,
        allowSlideNext: isMobile ? true : true,
        // centeredSlides: true,
        autoplay: {
          delay: 4000,
          disableOnInteraction: true,
        },
        loop: true,
        // effect: 'fade',
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },
      },
      slideList: [
        {
          img: require('./s9/img1.jpg'),
          title: '升級結構安全－捆筋與梁柱接續',
          desc:
            '鋼筋特別選用成本較高的熱軋鋼筋，落實緊密箍筋135度的要求，使用SA級套筒壓接鋼筋續接器，讓結構安全滴水不漏！',
        },
        {
          img: require('./s9/img2.jpg'),
          title: '結構體更穩固－筏式基礎',
          desc:
            '筏式基礎的承載面積大，能減小基底壓力，增加基礎剛度，當發生天災時，基礎之間的相互支援性較強，可大大降低房子地基的撕裂危機。',
        },
        {
          img: require('./s9/img3.jpg'),
          title: '確實紮穩根基－連續壁',
          desc:
            '在地下室施作一道周圍閉合的擋土牆，外側的土壤及地下水不會崩坍或滲入基地內，同時也能夠作為地下室的外牆，成為主要結構體的一部分。京城鳳翔連續壁厚度50ＣＭ，連續壁深度19米，深入地底穩定層，確保施工品質與安全。',
        },
      ],
    }
  },

  methods: {
    slideChanged(e) {
      const swiper = this.$refs.mySwiper.swiper
      if (this.isMobile) {
        if (swiper.activeIndex === 5) {
          this.slideIndex = 0
        } else if (swiper.activeIndex === 4) {
          this.slideIndex = 2
        } else {
          this.slideIndex = 1
        }
      } else {
        if (swiper.isEnd) {
          this.slideIndex = 0
        } else if (swiper.isBeginning) {
          this.slideIndex = swiper.slides.length - 3
        } else {
          this.slideIndex = swiper.activeIndex - 1
        }
      }
    },
  },
}
</script>
