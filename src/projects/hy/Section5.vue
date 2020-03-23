<template>
  <div class="section5">
    <div class="bg">
      <div v-if="!isMobile">
        <img src="./s5/bg.jpg" alt class="bg-img" />
        <div class="content" data-aos="fade-left" data-aos-delay="200">
          <div class="title">
            全台最大Costco
            <br />置產跟著國際財團走
          </div>
          <div class="desc">
            全球零售商龍頭，開店首選交通核心及人口密度高區域
            <br />磁吸消費人口，帶動黃金地段持續增值
          </div>
        </div>
      </div>
      <div v-else>
        <div class>
          <!-- <img src="./s3/mo/1.jpg" alt class="img" data-aos="zoom-in" data-aos-delay="200" /> -->
          <img src="./s5/mo/bg.jpg" alt class="bg-img" />
          <div class="content" data-aos="fade-down" data-aos-delay="200">
            <div class="title">
              全台最大Costco
              <br />置產跟著國際財團走
            </div>
            <div class="desc">
              全球零售商龍頭，開店首選交通核心及人口密度高區域
              <br />磁吸消費人口，帶動黃金地段持續增值
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
  right: calc(100vw * 130 / 1920);
  top: calc(100vh * 400 / 940);
}

.title {
  font-size: calc(100vw * 70 / 1920);
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.09;
  letter-spacing: normal;
  text-align: left;
  color: #ffffff;
  margin-bottom: 20px;
}

.desc {
  font-size: calc(100vw * 26 / 1920);
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.47;
  letter-spacing: normal;
  text-align: left;
  color: #ffffff;
}

@media only screen and (max-width: 1280px) and (min-width: 1025px) {
  .fullscreen {
    height: 100vh;
  }

  .content {
    top: calc(100vh * 650 / 940);
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
    top: calc(100vh * 280 / 940);
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
    bottom: calc(100vh * 100 / 675);
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
  name: 'section5',

  data() {
    return {
      isMobile,
    }
  },

  methods: {},
}
</script>
