<template>
  <div class="section3">
    <div class="bg">
      <img src="./s3/bg.jpg" alt="" class="bg-img">
      <div v-if="!isMobile">
        <swiper :options="swiperOption" ref="mySwiper" data-aos="fade-right" data-aos-delay="600">
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
        <div class="content">
          <div class="title" data-aos="fade-left" data-aos-delay="400">繁華第一光圈</div>
          <div class="subtitle" data-aos="fade-left" data-aos-delay="600">FOCUS SPOTLIGHT</div>
          <div class="desc" data-aos="fade-left" data-aos-delay="800">聚富雙核心，萬中選一最佳地段</div>
          <div class="item-title" data-aos="fade-left" data-aos-delay="900">中平幸福路J-MART百貨商圈</div>
          <div class="item-desc" data-aos="fade-left" data-aos-delay="1000">中正新泰路、中平幸福路商圈繁華雙核心，「璽園」身價當然最高貴，散步即達J-MART佳瑪百貨，家樂福、麥當勞等更近在咫尺。</div>
          <div class="item-title" data-aos="fade-left" data-aos-delay="1100">雙十字交通軸線中心點與主動脈</div>
          <div class="item-desc" data-aos="fade-left" data-aos-delay="1200">雙十字軸線交通重心，台一線、65快速道路、新泰及泰林路等，速達泰山、三重、板橋等地，新北大道快速直達台北市區。</div>
          <div class="item-title" data-aos="fade-left" data-aos-delay="1300">鄰近萬坪運動公園與千米綠廊帶</div>
          <div class="item-desc" data-aos="fade-left" data-aos-delay="1400">公園生活圈房價永遠最保值，「璽園」鄰近22公頃新莊運動公園、中港綠堤公園，串聯成超過千米的綠色休閒廊帶。</div>
          <div class="item-title" data-aos="fade-left" data-aos-delay="1500">方圓之內名校藝文中心密度最高</div>
          <div class="item-desc" data-aos="fade-left" data-aos-delay="1600">讓孩子贏在起跑點，優質學區包括榮富國小、中平國中、新莊高中，以及新莊社區大學、文化藝術中心等，藝文氣息濃厚。</div>
        </div>
      </div>
      <div v-else>
        <div class="content">
          <div class="title" data-aos="fade-right" data-aos-delay="600">繁華第一光圈</div>
          <div class="subtitle" data-aos="fade-right" data-aos-delay="800">FOCUS SPOTLIGHT</div>
          <div class="desc" data-aos="fade-right" data-aos-delay="1000">聚富雙核心，萬中選一最佳地段</div>
        </div>
        <div class="dropdown" data-aos="fade-right" data-aos-delay="1200">
          <div
            :class="`item ${item.open ? 'open' : ''}`"
            v-for="(item, index) in toggleList"
            :key="item.title"
          >
            <h3 @click="toggle(index)" class="head flex-jb flex-ac">
              <div>{{item.title}}</div>
              <img v-if="!item.open" src="./plus.png" alt class="btn" />
              <img v-if="item.open" src="./minus.png" alt class="btn" />
            </h3>
            <div class="desc" v-html="item.desc"></div>
          </div>
        </div>
        <swiper :options="swiperOption" ref="mySwiper" data-aos="fade-right" data-aos-delay="1000">
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
  background-size: cover;
  background-position: center;
  position: relative;
  overflow: hidden;
  padding-top: 220px;
  height: calc(100vw * 1050 / 1680);

  > div {
    display: flex;
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

  // &:nth-child(1) {
  //   position: relative;
  // }
}

.item-img {
  &:nth-child(1) {
    position: relative;
  }
  width: 50vw;
  position: absolute;
}

.swiper-container {
  width: 50vw;
}

.content {
  width: 50vw;
  padding-left: 65px;
  position: relative;
  z-index: 1;
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

.desc {
  font-size: calc(100vw * 26 / 1920);
  font-weight: normal;
  font-style: normal;
  font-stretch: normal;
  line-height: 1.46;
  letter-spacing: normal;
  text-align: left;
  color: #91b260;
  margin-bottom: calc(100vw * 50 / 1920);
}

.item-title {
  font-size: calc(100vw * 20 / 1920);
  font-weight: normal;
  font-style: normal;
  font-stretch: normal;
  line-height: 1.9;
  letter-spacing: normal;
  text-align: left;
  color: #b7004c;
  margin-bottom: 0px;
}

.item-desc {
  width: 585px;
  font-size: calc(100vw * 18 / 1920);
  font-weight: normal;
  font-style: normal;
  font-stretch: normal;
  line-height: 2.11;
  letter-spacing: normal;
  text-align: left;
  color: #444444;
  margin-bottom: calc(100vw * 30 / 1920);
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
    padding: 180px 0;
  }

  .bg-img {
    top: 0;
    bottom: 0;
    height: auto;
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
    height: auto;

    > div {
      display: block;
      position: relative;
      z-index: 1;
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

  .desc {
    font-size: 17.5px;
    font-weight: normal;
    font-style: normal;
    font-stretch: normal;
    line-height: 1.49;
    letter-spacing: normal;
    text-align: left;
    color: #91b260;
  }

  .swiper-container {
    width: 100vw;
    margin-top: 25px;
  }

  .content {
    width: 100vw;
    background-image: url('./mobg.jpg');
    background-size: cover;
    padding: 50px 20px 45px;
  }

  .dropdown {
    .item {
      height: 40px;
      overflow: hidden;
      border-bottom: solid 0.5px #595757;
      width: calc(100vw * 670 / 750);
      margin: 0 auto;
      transition: all 0.5s;

      &.open {
        height: auto;
      }
    }
    .head {
      font-size: 16.5px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      line-height: 40px;
      letter-spacing: normal;
      text-align: left;
      color: #b7004c;
    }

    .btn {
      width: 18px;
    }

    .desc {
      padding-top: 0px;
      padding-bottom: 10px;
      font-size: 15px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.73;
      letter-spacing: normal;
      text-align: justify;
      color: #444444;
    }
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
  name: 'section3',
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
          src: require('./s3/1.jpg'),
        },
        {
          src: require('./s3/2.jpg'),
        },

        {
          src: require('./s3/3.jpg'),
        },
        {
          src: require('./s3/4.jpg'),
        },
      ],
      toggleList: [
        {
          title: '中平幸福路J-MART百貨商圈',
          desc:
            '中正新泰路、中平幸福路商圈繁華雙核心，「璽園」身價當然最高貴，散步即達J-MART佳瑪百貨，家樂福、麥當勞等更近在咫尺。',
          open: true,
        },
        {
          title: '雙十字交通軸線中心點與主動脈',
          desc:
            '雙十字軸線交通重心，台一線、65快速道路、新泰及泰林路等，速達泰山、三重、板橋等地，新北大道快速直達台北市區。',
          open: false,
        },
        {
          title: '鄰近萬坪運動公園與千米綠廊帶',
          desc:
            '公園生活圈房價永遠最保值，「璽園」鄰近22公頃新莊運動公園、中港綠堤公園，串聯成超過千米的綠色休閒廊帶。',
          open: false,
        },
        {
          title: '方圓之內名校藝文中心密度最高',
          desc:
            '讓孩子贏在起跑點，優質學區包括榮富國小、中平國中、新莊高中，以及新莊社區大學、文化藝術中心等，藝文氣息濃厚。',
          open: false,
        },
      ],
    }
  },

  methods: {
    toggle(index) {
      if (this.toggleList[index].open) {
        this.toggleList[index].open = false
      } else {
        this.toggleList.forEach(item => (item.open = false))
        this.toggleList[index].open = !this.toggleList[index].open
      }
    },
  },
}
</script>
