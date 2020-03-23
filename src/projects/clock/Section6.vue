<template>
  <div class="section6">
    <div class="bg">
      <div v-if="!isMobile">
        <img v-lazy="require('./s6/bg.png')" alt class="bg-img" />
        <img
          v-lazy="require('./s6/bgimg.png')"
          alt
          class="bg-img fix"
          data-aos="fade"
          data-aos-delay="300"
        />
        <div class="block-img" data-aos="fade" data-aos-delay="300">
          <div class="relative">
            <img v-lazy="require('./s6/img.jpg')" alt />
            <div class="block-title">外觀3D示意圖</div>
          </div>
        </div>
        <div class="content">
          <div class="title">金獎冠冕加身 堅強厚實力</div>
          <div
            class="desc"
          >京城建設於2016年推出的【京城京城】，不僅為高雄指標豪宅，更榮獲內政部耐震、綠建築雙標章認證，以及第24屆中華建築金石獎施工品質類住宅超高層組的金石首獎！經國際級獎項與背書，品牌實力有目共睹</div>
          <div class="subtitle">京城集團近年沿革</div>
          <div class="desc">
            <div class="text">
              2016－工期長達6年的農十六案【京城京城】完工<br />
              獲內政部耐震建築、綠建築標章認證，並<br />
              榮獲建築金石獎首獎<br />
              2016－京城總部大樓遷移至博愛二路150號<br />
              2016－與「台灣建築安全履歷協會」簽約<br />
              為中南部首家導入「建築安全履歷」建商
            </div>
            <div class="text">
              2017－京城博愛路新企業總部落成、喬遷<br />
              2017－京城建設100%轉投資H20水京機國際酒店開幕<br />
              2018－【圓山大院】榮獲南台灣建築園冶獎等六大獎項<br />
              2019－【時尚京城】榮獲2019南台灣建築園治獎<br />
              2019－【京城美術皇居】、【時尚京城】、【閱河堤】<br />
              與【圓山天墅】共獲得高雄厝、綠建築等五座獎項
            </div>
          </div>
        </div>
      </div>
      <div v-else>
        <img v-lazy="require('./mo/6/bg.png')" alt class="bg-img" />
        <img
          v-lazy="require('./mo/6/bgimg.png')"
          alt
          class="bg-img fix"
          data-aos="fade"
          data-aos-delay="300"
        />
        <div class="block-img" data-aos="fade" data-aos-delay="300">
          <div class="relative">
            <img v-lazy="require('./mo/6/img.png')" alt />
          </div>
        </div>
        <div class="content">
          <div class="title">金獎冠冕加身 堅強厚實力</div>
          <div
            class="desc"
          >京城建設於2016年推出的【京城京城】，不僅為高雄指標豪宅，更榮獲內政部耐震、綠建築雙標章認證，以及第24屆中華建築金石獎施工品質類住宅超高層組的金石首獎！經國際級獎項與背書，品牌實力有目共睹</div>
          <div class="subtitle">京城集團近年沿革</div>
          <div class="desc">
            <div class="text">
              2016－工期長達6年的農十六案【京城京城】完工<br />
              獲內政部耐震建築、綠建築標章認證，並<br />
              榮獲建築金石獎首獎<br />
              2016－京城總部大樓遷移至博愛二路150號<br />
              2016－與「台灣建築安全履歷協會」簽約<br />
              為中南部首家導入「建築安全履歷」建商
            </div>
            <div class="text">
              2017－京城博愛路新企業總部落成、喬遷<br />
              2017－京城建設100%轉投資H20水京機國際酒店開幕<br />
              2018－【圓山大院】榮獲南台灣建築園冶獎等六大獎項<br />
              2019－【時尚京城】榮獲2019南台灣建築園治獎<br />
              2019－【京城美術皇居】、【時尚京城】、【閱河堤】<br />
              與【圓山天墅】共獲得高雄厝、綠建築等五座獎項
            </div>
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
  height: size(1150);
  display: flex;
  align-items: center;
  z-index: 0;

  > div {
    display: flex;
    align-items: center;
  }
}

.bg-img {
  width: 100vw;
  height: auto;
  position: absolute;
  top: 0;
  left: 0;
  display: block;
  object-fit: cover;
  z-index: 1;

  &.fix {
    position: fixed;
  }

  &:nth-child(1) {
    // position: relative;
  }
}

.block-img {
  position: absolute;
  left: size(0);
  bottom: size(150);
  width: size(935);
  z-index: 3;

  img {
    width: 100%;
  }
}

.block-title {
  font-size: size(16);
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

.content {
  position: absolute;
  width: size(729);
  top: size(460);
  right: size(142);
  z-index: 2;
}

.title {
  font-size: size(40);
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #000000;
  margin-bottom: size(10);
}

.desc {
  font-size: size(15);
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 2.4;
  letter-spacing: normal;
  text-align: left;
  color: #000000;
  margin-bottom: size(20);
}

.subtitle {
  font-size: size(24);
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.5;
  letter-spacing: normal;
  text-align: left;
  color: #000000;
  margin-bottom: size(10);
}

.text {
  width: 50%;
  display: inline-block;
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
    height: size-m(957);
    display: block;
    z-index: 2;
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
    z-index: 3;

    // &:nth-child(1) {
    //   position: relative;
    // }
  }

  .block-img {
    width: 100vw;
    top: 0;
    left: 0;
    right: 0;
    margin: 0 auto;
  }

  .content {
    width: size-m(313);
    left: 0;
    right: 0;
    top: size-m(350);
    margin: 0 auto;
    z-index: 5;
  }

  .title {
    font-size: size-m(22);
  }

  .desc {
    font-size: size-m(12);
    width: 100%;
    display: block;
  }

  .subtitle {
    font-size: size-m(13);
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

export default {
  name: 'section6',

  data() {
    return {
      isMobile,
      isTablet,
    }
  },

  methods: {},
}
</script>
