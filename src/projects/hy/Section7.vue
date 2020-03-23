<template>
  <div class="section7">
    <div class="bg">
      <div v-if="!isMobile">
        <img src="./s7/bg.jpg" alt class="bg-img" />
        <div class="content" data-aos="fade-left" data-aos-delay="200">
          <div class="title">
            中央大學
            <br />學府文化圈
          </div>
          <div class="desc">
            全球最佳大學排名連續四年超前交大
            <br />全台「中」字輩教育龍頭
            <br />前六頂尖研究型大學，不定時舉辦展覽講座
            <br />讓孩子從小培養非凡眼界
          </div>
        </div>
      </div>
      <div v-else>
        <div class>
          <!-- <img src="./s3/mo/1.jpg" alt class="img" data-aos="zoom-in" data-aos-delay="200" /> -->
          <img src="./s7/mo/bg.jpg" alt class="bg-img" />
          <div class="content" data-aos="fade-down" data-aos-delay="200">
            <div class="title">
              中央大學
              <br />學府文化圈
            </div>
            <div class="desc">
              全球最佳大學排名連續四年超前交大
              <br />全台「中」字輩教育龍頭
              <br />前六頂尖研究型大學，不定時舉辦展覽講座
              <br />讓孩子從小培養非凡眼界
            </div>
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

.content {
  position: absolute;
  right: calc(100vw * 108 / 1920);
  top: calc(100vh * 480 / 940);
}

.title {
  font-size: calc(100vw * 68 / 1920);
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.09;
  letter-spacing: normal;
  text-align: right;
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
  text-align: right;
  color: #ffffff;
}

@media only screen and (max-width: 1280px) and (min-width: 1025px) {
  .fullscreen {
    height: 100vh;
  }

  .content {
    top: calc(100vh * 720 / 940);
  }
}

/* 螢幕尺寸標準 */
/* 平板尺寸 */
@media only screen and (min-device-width: 768px) and (max-device-width: 1024px) {
  .bg {
  }

  .bg-img {
    top: 0;
    bottom: 0;
    height: auto;
  }

  .content {
    top: calc(100vh * 350 / 940);
  }
}

@media screen and (max-width: 767px) {
  .bg {
    // background-size: 100% 100%;
  }

  .content {
    position: absolute;
    left: auto;
    right: calc(100vw * 24 / 375);
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
    text-align: right;
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
    text-align: right;
    color: #ffffff;
  }
}
</style>
<script>
// @ is an alias to /src
import { isMobile } from '@/utils'

export default {
  name: 'section7',

  data() {
    return {
      isMobile,
    }
  },

  methods: {},
}
</script>
