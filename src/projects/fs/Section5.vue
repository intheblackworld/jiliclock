<template>
  <div class="section5">
    <div class="bg">
      <div v-if="!isMobile">
        <img v-lazy="require('./s5/bg.png')" alt class="bg-img" />
        <img v-lazy="require('./s5/logo.png')" alt class="bg-img" />
        <div class="swiper-button-prev" slot="button-prev">
          <img src="./all/箭頭2.png" alt />
        </div>
        <div class="swiper-button-next" slot="button-next">
          <img src="./all/箭頭1.png" alt />
        </div>
        <transition-group name="slide-fade" mode="out-in">
          <div
            class="content"
            v-for="(slide, index) in slideList"
            v-show="index === slideIndex"
            :key="slide.img1"
          >
            <div class="title" v-html="slideList[slideIndex].title"></div>
            <div class="desc" v-html="slideList[slideIndex].desc"></div>
          </div>
        </transition-group>
        <swiper
          :options="swiperOption"
          ref="mySwiper"
          data-aos="fade"
          data-aos-delay="200"
          class="swiper-r"
          @slideChangeTransitionEnd="slideChanged"
        >
          <swiper-slide
            v-for="(slide, index) in slideList"
            :index="index"
            :key="slide.img1"
            class="item"
          >
            <img :src="slide.img1" :class="`item-img`" />
            <div class="item-title" v-html="slide.name"></div>
          </swiper-slide>
        </swiper>
        <swiper
          :options="swiperOption"
          ref="mySwiper"
          data-aos="fade"
          data-aos-delay="200"
          class="swiper-l"
        >
          <swiper-slide
            v-for="(slide, index) in slideList"
            :index="index"
            :key="slide.img2"
            class="item"
          >
            <img :src="slide.img2" :class="`item-img`" />
            <div class="item-title" v-html="slide.name"></div>
          </swiper-slide>
        </swiper>
      </div>
      <div v-else>
        <img v-lazy="require('./mo/5/bg.png')" alt class="bg-img" />
        <img v-lazy="require('./mo/5/logo.png')" alt class="bg-img" />
        <div class="swiper-button-prev" slot="button-prev">
          <img src="./all/箭頭2.png" alt />
        </div>
        <div class="swiper-button-next" slot="button-next">
          <img src="./all/箭頭1.png" alt />
        </div>
        <transition-group name="slide-fade" mode="out-in">
          <div
            class="content"
            v-for="(slide, index) in slideList"
            v-show="index === slideIndex"
            :key="slide.img1"
          >
            <div class="title" v-html="slideList[slideIndex].title"></div>
            <div class="desc" v-html="slideList[slideIndex].desc"></div>
          </div>
        </transition-group>
        <swiper
          :options="swiperOption"
          ref="mySwiper"
          data-aos="fade"
          data-aos-delay="200"
          class="swiper-r"
          @slideChangeTransitionEnd="slideChanged"
        >
          <swiper-slide
            v-for="(slide, index) in slideList"
            :index="index"
            :key="slide.img1"
            class="item"
          >
            <img :src="slide.img1" :class="`item-img`" />
            <!-- <div class="item-title" v-html="slide.name"></div> -->
          </swiper-slide>
        </swiper>
        <swiper
          :options="swiperOption"
          ref="mySwiper"
          data-aos="fade"
          data-aos-delay="200"
          class="swiper-l"
        >
          <swiper-slide
            v-for="(slide, index) in slideList"
            :index="index"
            :key="slide.img2"
            class="item"
          >
            <img :src="slide.img2" :class="`item-img`" />
            <!-- <div class="item-title" v-html="slide.name"></div> -->
          </swiper-slide>
        </swiper>
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
  height: calc(100vw * 960 / 1920);
  display: flex;
  align-items: center;
  z-index: 1;
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

.content {
  width: calc(100vw * 690 / 1920);
  z-index: 1;
  left: calc(100vw * 200 / 1920);
  top: calc(100vw * 290 / 1920);
  position: absolute;
}

.title {
  font-size: calc(100vw * 40 / 1920);
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #ffffff;
  margin-bottom: calc(100vw * 15 / 1920);
}

.desc {
  font-size: calc(100vw * 16 / 1920);
  font-size: 16px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 2.25;
  letter-spacing: normal;
  text-align: left;
  color: #b7d5d6;
}

.swiper-r {
  width: calc(100vw * 740 / 1920);
  right: calc(100vw * 100 / 1920);
  top: 0;
  left: auto;
  position: absolute;
}

.swiper-l {
  width: calc(100vw * 682 / 1920);
  left: calc(100vw * 203 / 1920);
  bottom: 0;
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
    height: size-m(550);
    display: block;

    img {
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
    height: auto;
    display: block;
    object-fit: cover;
    z-index: 0;
    // mix-blend-mode: screen;

    // &:nth-child(1) {
    //   position: relative;
    // }
  }

  .content {
    width: size-m(315);
    position: absolute;
    left: 0;
    right: 0;
    margin: 0 auto;
    top: size-m(220);
  }

  .title {
    font-size: size-m(22);
    margin: 0 auto;
    font-weight: bold;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.48;
    letter-spacing: 2.32px;
    text-align: left;
    color: #ffffff;
    margin-bottom: size-m(17);
  }

  .desc {
    font-size: size-m(12);
    margin: 0 auto;
    font-weight: normal;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.58;
    letter-spacing: 0.48px;
    text-align: left;
    color: #cccccc;
  }

  .swiper-r {
    width: 100vw;
    left: 0;
    right: 0;
    margin: 0 auto;
    top: 0;
  }

  .swiper-l {
    width: 100vw;
    left: 0;
    right: 0;
    margin: 0 auto;
    top: 0;
  }

  .item-title {
    font-size: size-m(12);
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
      isHide: true,
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
          img1: isMobile ? require('./mo/5/img1-1.png') : require('./s5/img1-1.jpg'),
          img2: isMobile ? require('./mo/5/img1-2.png') : require('./s5/img1-2.jpg'),
          name: 'H2O水京棧國際酒店',
          title: '京城集團邁步卓越<br />金獎冠冕 實力之作',
          desc:
            '京城集團創立於1982年，為目前台灣數一數二的企業集團，跨足建設、營造、飯店產業：京城建設、京城飯店、H2O水京棧國際酒店，整合了近40年經驗，以堅強實力造就每件精彩作品，其中「京城京城」、「京城美術皇居」更開啟了高雄豪宅的新眼界，同時也是國際建築獎項常勝軍，包含「京城樂活、「京城鉅誕」、「京城凱悅」等案，業績閃耀南台灣！',
        },
        {
          img1: isMobile ? require('./mo/5/img2-1.png') : require('./s5/img2-1.jpg'),
          img2: isMobile ? require('./mo/5/img2-2.png') : require('./s5/img2-2.jpg'),
          name: '京城鉅誕',
          title: '建築安全新突破<br />勇於挑戰 精益求精',
          desc:
            '京城的房子不只在生活美學上求新求變，更在建築結構安全上，更投入了龐大的人力、物力，在南台灣建築業界無人能及，陸續導入SRC鋼骨混凝土結構、BRB斜撐制震、美國EPS制震壁、中空樓板、耐震系統工法及建築安全履歷、甚至更嚴格的國家級耐震標章認證。',
        },
        {
          img1: isMobile ? require('./mo/5/img3-1.png') : require('./s5/img3-1.jpg'),
          img2: isMobile ? require('./mo/5/img3-2.png') : require('./s5/img3-2.jpg'),
          name: '京城King park',
          title: '豪宅資歷 無懈可擊<br />高雄奢華傳奇－京城KING PARK',
          desc:
            '京城集團深耕高雄，一路走來以穩健實力建立建築王國。位農16特區綠海首排的「京城KING PARK」，以東方版Art Deco建築，為高雄天際線添上一筆世界級奢華！做工繁複的竹節立面，以萬噸岡石精工打造總裁級居邸，建材更是遍尋五大洲的萬中選一，在空間設計寫下了輝煌鎏金歲月，由內到外的尊榮珍貴，見證京城品牌深厚能量。',
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
