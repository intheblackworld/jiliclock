<template>
  <div class="section3">
    <div class="bg">
      <div v-if="!isMobile">
        <img
          v-lazy="require('./s3/bg.png')"
          alt
          class="bg-img"
          data-aos="fade"
          data-aos-delay="300"
        />
        <div class="relative">
          <img
            v-lazy="require('./s3/img2.png')"
            alt
            class="img"
            data-aos="fade"
            data-aos-delay="300"
          />
          <img
            v-lazy="require('./s3/img1.jpg')"
            alt
            class="l-img"
            data-aos="fade"
            data-aos-delay="300"
          />
          <div class="content-t">
            <div class="title">落點校園首排 舞動雙站捷奏</div>
            <div class="subtitle">天天公園孵育生活美好，轉身接軌鳳山國中站、大寮站</div>
            <div class="desc">
              ■ 享受無限棟距好視野，開窗就是天天公園&學校預定地
              <br />■ 跟著捷運經濟走，散步5分鐘，連接鳳山國中、大寮捷運站
              <br />■ 學區完整，以單車的距離，遇見中正國小、鳳山國中、新光高中
              <br />■ 生活機能齊全，與後庄中庄、鳳林、輔英商圈為鄰
              <br />■ 車行即串聯台1線、台25線，快速連通大高雄
              <br />■ 10分鐘內，與鳳山火車站接軌，精采生活無往不利
            </div>
          </div>
        </div>
        <div class="relative">
          <img
            :src="require('./s3/img3.jpg')"
            alt
            class="r-img"
            data-aos="fade"
            data-aos-delay="300"
          />
          <div class="content-b">
            <div class="subtitle">增值起步走！起漲向東看！</div>
            <div class="title">再造高雄新東區</div>
            <div class="desc">
              紐約、新加坡等國際城市都呈現「向東發展」趨勢，鳳山位高雄都會核心東側，同時也是高雄行政區人口數第一名，不僅人口潛力持續攀升，建設實力也不容小覷。
              <br />
              <br />南台灣最大兩座藝術殿堂衛武營國家文化藝術中心、大東藝術中心座落於此，曹公圳親水計畫、環城自行車道、國道7號計畫等共10大建設共投入超過千億資金，有效提升了居住機能品質，連帶帶動鳳山身價，大大推動城市位階，高雄新東區未來可看性無可限量！
            </div>
          </div>
        </div>
        <div class="bottom">
          <div class="blue"></div>
          <img v-lazy="require('./s3/4-1.jpg')" alt data-aos="fade" data-aos-delay="300" />
          <img v-lazy="require('./s3/4-2.jpg')" alt data-aos="fade" data-aos-delay="300" />
          <img v-lazy="require('./s3/4-3.jpg')" alt data-aos="fade" data-aos-delay="300" />
          <div class="blue"></div>
        </div>
      </div>
      <div v-else>
        <img
          v-lazy="require('./mo/3/img2.png')"
          alt
          class="bg-img"
          data-aos="fade"
          data-aos-delay="300"
        />
        <img
          v-lazy="require('./mo/3/img1.jpg')"
          alt
          class="bg-img"
          data-aos="fade"
          data-aos-delay="300"
        />
        <div class="content-t">
          <div class="title">落點校園首排 舞動雙站捷奏</div>
          <div class="subtitle">天天公園孵育生活美好，轉身接軌鳳山國中站、大寮站</div>
          <div class="desc">
            ■ 享受無限棟距好視野，開窗就是天天公園&學校預定地
            <br />■ 跟著捷運經濟走，散步5分鐘，連接鳳山國中、大寮捷運站
            <br />■ 學區完整，以單車的距離，遇見中正國小、鳳山國中、新光高中
            <br />■ 生活機能齊全，與後庄中庄、鳳林、輔英商圈為鄰
            <br />■ 車行即串聯台1線、台25線，快速連通大高雄
            <br />■ 10分鐘內，與鳳山火車站接軌，精采生活無往不利
          </div>
        </div>
        <div class="img-b">
          <swiper
            :options="swiperOption"
            ref="mySwiper"
            data-aos="fade"
            data-aos-delay="200"
            class
            @slideChangeTransitionEnd="slideChanged"
          >
            <swiper-slide
              v-for="(slide, index) in slideList"
              :index="index"
              :key="slide.img"
              class="item"
            >
              <img :src="slide.img" :class="`item-img`" />
              <div class="item-title" v-html="slide.name"></div>
            </swiper-slide>
          </swiper>
        </div>

        <div class="content-b">
          <div class="subtitle">增值起步走！起漲向東看！</div>
          <div class="title">再造高雄新東區</div>
          <div class="desc">
            紐約、新加坡等國際城市都呈現「向東發展」趨勢，鳳山位高雄都會核心東側，同時也是高雄行政區人口數第一名，不僅人口潛力持續攀升，建設實力也不容小覷。
            <br />
            <br />南台灣最大兩座藝術殿堂衛武營國家文化藝術中心、大東藝術中心座落於此，曹公圳親水計畫、環城自行車道、國道7號計畫等共10大建設共投入超過千億資金，有效提升了居住機能品質，連帶帶動鳳山身價，大大推動城市位階，高雄新東區未來可看性無可限量！
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
  height: calc(100vw * 1750 / 1920);
  z-index: 1;
}
.bg-img {
  width: 100vw;
  height: auto;
  position: absolute;
  top: 0;
  left: 0;
  display: block;
  object-fit: cover;
}
.img {
  width: 100vw;
  height: auto;
  position: absolute;
  top: 0;
  left: 0;
  display: block;
  object-fit: cover;
  z-index: 2;

  &:nth-child(1) {
    position: relative;
    z-index: 2;
  }
}

.l-img {
  position: absolute;
  width: calc(100vw * 1130 / 1920);
  height: auto;
  left: calc(100vw * 32 / 1920);
  top: calc(100vw * 80 / 1920);
}

.r-img {
  position: absolute;
  width: calc(100vw * 960 / 1920);
  height: auto;
  right: calc(100vw * 0 / 1920);
  top: calc(100vw * -100 / 1920);
  z-index: 1;
}

.content-t {
  position: absolute;
  top: calc(100vw * 150 / 1920);
  right: calc(100vw * 111 / 1920);
}

.content-b {
  position: absolute;
  top: calc(100vw * 40 / 1920);
  left: calc(100vw * 130 / 1920);
  width: calc(100vw * 635 / 1920);
}

.title {
  font-size: calc(100vw * 40 / 1920);
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #000000;
  margin-bottom: calc(100vw * 15 / 1920);
}

.subtitle {
  font-size: calc(100vw * 23 / 1920);
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.48;
  letter-spacing: normal;
  text-align: left;
  color: #000000;
  margin-bottom: calc(100vw * 20 / 1920);
}

.desc {
  font-size: calc(100vw * 16 / 1920);
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 2.25;
  letter-spacing: normal;
  text-align: left;
  color: #666666;
}

.item-title {
  font-size: calc(100vw * 24 / 1920);
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.58;
  letter-spacing: 0.48px;
  text-align: right;
  color: #ffffff;
  position: absolute;
  right: 20px;
  bottom: 10px;
}

.bottom {
  width: 100vw;
  position: absolute;
  height: calc(100vw * 330 / 1920);
  display: flex;
  justify-content: space-between;
  bottom: 0;

  img {
    width: calc(100vw * 550 / 1920);
  }

  .blue {
    width: calc(100vw * 90 / 1920);
    height: 100%;
    background-color: #20969b;
  }
}

@media only screen and (max-width: 1280px) and (min-width: 1025px) {
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
    display: block;
    height: size-m(1365);

    > div {
      display: block;
    }
  }

  .swiper-container {
    width: 100vw;
    position: relative;
  }

  .bg-img {
    width: 100vw;
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    height: auto;
    display: block;
    object-fit: cover;
    z-index: 3;

    &:nth-child(1) {
      position: relative;
    }
  }

  .content-t {
    width: 90vw;
    position: absolute;
    left: 0;
    right: 0;
    margin: 0 auto;
    top: size-m(252);
  }

  .content-b {
    width: 90vw;
    position: absolute;
    left: 0;
    right: 0;
    margin: 0 auto;
    top: size-m(982);
  }

  .title {
    font-size: size-m(22);
  }

  .subtitle {
    font-size: size-m(13);
  }

  .desc {
    font-size: size-m(12);
  }

  .img-b {
    width: 100vw;
    position: absolute;
    top: size-m(690);
    left: 0;
  }

  .item-img {
    width: 100%;
  }

  .item-title {
    font-size: calc(100vw * 14 / 375);
    font-weight: normal;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.58;
    letter-spacing: 0.48px;
    text-align: right;
    color: #ffffff;
    position: absolute;
    right: 20px;
    bottom: 10px;
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
  name: 'section3',
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
          img: require('./mo/3/img3.jpg'),
        },
        {
          img: require('./mo/3/4-1.jpg'),
        },
        {
          img: require('./mo/3/4-2.jpg'),
        },
        {
          img: require('./mo/3/4-3.jpg'),
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
