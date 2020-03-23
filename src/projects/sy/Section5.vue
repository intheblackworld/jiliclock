<template>
  <div class="section5">
    <div class="bg fullscreen">
      <div v-if="!isMobile">
        <div class="left">
          <div class="content">
            <div class="title" data-aos="fade-right" data-aos-delay="600">安全第一優先</div>
            <div class="subtitle" data-aos="fade-right" data-aos-delay="700">FIRST PRIORITY</div>
            <div class="desc" data-aos="fade-right" data-aos-delay="800">安全制震宅，打造堅若磐石城堡</div>
            <div class="dropdown" data-aos="fade-right" data-aos-delay="900">
              <div
                :class="`item ${item.open ? 'open' : ''}`"
                v-for="(item, index) in toggleList"
                :key="item.title"
              >
                <h3 @click="toggle(index)" class="head flex-jb flex-ac">
                  <div>{{item.title}}</div>
                  <img v-if="!item.open" src="./s5/plus.png" alt class="btn" />
                  <img v-if="item.open" src="./s5/minus.png" alt class="btn" />
                </h3>
                <div class="item-desc" v-html="item.desc"></div>
              </div>
            </div>
          </div>
        </div>
        <div class="right" data-aos="fade-up" data-aos-delay="600">
          <img src="./s5/1.png" alt class="img" />
        </div>
      </div>
      <div v-else>
        <div class="content">
          <div class="title" data-aos="fade-right" data-aos-delay="600">安全第一優先</div>
          <div class="subtitle" data-aos="fade-right" data-aos-delay="800">FIRST PRIORITY</div>
          <div class="desc" data-aos="fade-right" data-aos-delay="1000">安全制震宅，打造堅若磐石城堡</div>
        </div>
        <div class="dropdown" data-aos="fade-right" data-aos-delay="1200">
          <div
            :class="`item ${item.open ? 'open' : ''}`"
            v-for="(item, index) in toggleList"
            :key="item.title"
          >
            <h3 @click="toggle(index)" class="head flex-jb flex-ac">
              <div>{{item.title}}</div>
              <img v-if="!item.open" src="./s5/plus.png" alt class="btn" />
              <img v-if="item.open" src="./s5/minus.png" alt class="btn" />
            </h3>
            <div class="item-desc" v-html="item.desc"></div>
          </div>
        </div>
        <img src="./s5/m1.png" alt class="img" data-aos="fade-right" data-aos-delay="1000" />
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
  background-image: url('./s5/bg.jpg');

  > div {
    display: flex;
    height: 100%;
  }
}

.left,
.right {
  width: 50vw;
  height: 100%;
  position: relative;

  .img {
    position: absolute;
    right: 0;
    bottom: 0;
    width: 100%;
  }
}

.content {
  width: 50vw;
  height: 100%;
  display: flex;
  align-items: flex-end;
  justify-content: center;
  flex-direction: column;
}

.title {
  width: calc(100vw * 630 / 1920);
  font-size: calc(100vw * 58 / 1920);
  font-weight: normal;
  font-style: normal;
  font-stretch: normal;
  line-height: 0.66;
  letter-spacing: normal;
  text-align: left;
  color: #fff06e;
  margin-bottom: calc(100vw * 20 / 1920);
}

.subtitle {
  width: calc(100vw * 630 / 1920);
  font-size: calc(100vw * 22 / 1920);
  font-family: 'Abril Fatface', cursive;
  font-weight: normal;
  font-style: normal;
  font-stretch: normal;
  line-height: 1.73;
  letter-spacing: normal;
  text-align: left;
  color: #ffffff;
  margin-bottom: calc(100vw * 35 / 1920);
}

.desc {
  width: calc(100vw * 630 / 1920);
  font-size: calc(100vw * 26 / 1920);
  font-weight: normal;
  font-style: normal;
  font-stretch: normal;
  line-height: 1.46;
  letter-spacing: normal;
  text-align: left;
  color: #fff;
  margin-bottom: calc(100vw * 30 / 1920);
}

.dropdown {
  .item {
    width: 630px;
    height: 50px;
    overflow: hidden;
    background-color: rgba(0, 0, 0, 0.2);
    padding-left: 23px;
    padding-right: 23px;
    border-radius: 10px;
    width: calc(100vw * 630 / 1920);
    margin-bottom: 18px;
    transition: all 0.5s;

    &.open {
      height: auto;
    }
  }
  .head {
    font-size: 20px;
    font-weight: normal;
    font-style: normal;
    font-stretch: normal;
    line-height: 50px;
    letter-spacing: normal;
    text-align: left;
    color: #ffdc3b;
  }

  .btn {
    width: 24px;
  }

  .item-desc {
    padding-top: 0px;
    padding-bottom: 10px;
    font-size: 18px;
    font-weight: normal;
    font-style: normal;
    font-stretch: normal;
    line-height: 1.73;
    letter-spacing: normal;
    text-align: justify;
    color: #dae1bd;
  }
}

@media only screen and (max-width: 1280px) and (min-width: 1025px) {
  .fullscreen {
    min-height: 700px;
    height: 100vh !important;
  }
}

/* 螢幕尺寸標準 */
/* 平板尺寸 */
@media only screen and (min-device-width: 768px) and (max-device-width: 1024px) {
  .bg {
    padding: 180px 0;
  }

  .dropdown {
    .item {
      width: 630px;
      height: 50px;
      overflow: hidden;
      background-color: rgba(0, 0, 0, 0.2);
      padding-left: 23px;
      padding-right: 23px;
      border-radius: 10px;
      width: calc(100vw * 630 / 1920);
      margin-bottom: 18px;
      transition: all 0.5s;

      &.open {
        height: auto;
      }
    }
    .head {
      font-size: 16px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      line-height: 50px;
      letter-spacing: normal;
      text-align: left;
      color: #ffdc3b;
    }

    .btn {
      width: 20px;
    }

    .item-desc {
      padding-top: 0px;
      padding-bottom: 10px;
      font-size: 18px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.73;
      letter-spacing: normal;
      text-align: justify;
      color: #dae1bd;
    }
  }

  .desc {
    margin-bottom: calc(100vw * 20 / 1920);
  }
}

@media screen and (max-width: 767px) {
  .bg {
    background-size: 100% 100%;
    background-image: url('./s5/mbg.jpg');
    padding-top: 0;
    padding-bottom: 0;
    height: auto;

    > div {
      display: block;
      position: relative;
      z-index: 1;
    }


    .fullscreen {
      height: auto !important;
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
    color: #fff06e;
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
    color: #fff;
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
    color: #fff;
  }

  .content {
    width: 100vw;
    padding: 50px 17px;
    height: auto;
    // background-image: url('./mobg.jpg');
    display: block;
    background-size: cover;
    // padding: 50px 20px 45px;
    .title,
    .subtitle,
    .desc {
      width: auto;
    }
  }

  .dropdown {
    .item {
      height: 40px;
      overflow: hidden;
      background-color: rgba(0, 0, 0, 0.2);
      padding-left: 23px;
      padding-right: 23px;
      border-radius: 10px;
      width: calc(100vw * 670 / 750);
      margin: 0 auto;
      margin-bottom: 18px;
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
      color: #ffdc3b;
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
      color: #dae1bd;
    }
  }

  .img {
    position: relative;
    width: 100%;
  }
}
</style>
<script>
// @ is an alias to /src
import { isMobile } from '@/utils'
import slider from '@/mixins/slider.js'
import 'swiper/dist/css/swiper.css'

export default {
  name: 'section5',
  mixins: [slider],

  data() {
    return {
      isMobile,
      toggleList: [
        {
          title: '打造新莊豪宅至高的安全基準',
          desc:
            '安全是衡量豪宅第一要件，採用日本第一品牌住友GRAST制震壁，提升抗震係數至0.26G，獨家十大結構安全設計，打造新莊豪宅至高基準。',
          open: true,
        },
        {
          title: '採用日本第一品牌住友制震壁',
          desc:
            '四百年歷史的住友集團橡膠工業，研發出高阻尼橡膠制震系統，提高耐震能力，獲日本國寶級古蹟京都東本願寺、姬路城、熊本城等採用。',
          open: false,
        },
        {
          title: '獨家十大結構設計與紮實施工',
          desc:
            '①全棟128組制震器安全耐震<br />②結構外審通過高標準<br />③基礎埋深筏式基礎施工<br />④採用4200kg/cm²高拉力鋼筋<br />⑤4至6千磅高強度混凝土施工<br />⑥SA級續接器加強結構強度<br />⑦水平樓板加厚至18公分<br />⑧強柱弱梁設計吸收地震能量<br />⑨防止土壤液化連續壁施工<br />⑩專業結構設計與施工監造認證',
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
