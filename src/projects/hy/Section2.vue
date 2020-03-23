<template>
  <div class="section2">
    <div class="bg">
      <div v-if="!isMobile">
        <!-- <img src="./s2/map.jpg" alt class="bg-img" /> -->
        <img src="./s2/bg.jpg" alt class="bg-img" />
        <img src="./s2/title.png" alt class="bg-img" data-aos="fade-right" data-aos-delay="200" />
      </div>
      <div v-else>
        <div class>
          <!-- <img src="./s3/mo/1.jpg" alt class="img" data-aos="zoom-in" data-aos-delay="600" /> -->
          <img src="./s2/mo/bg.jpg" alt class="bg-img" />
          <div class="content" data-aos="fade-down" data-aos-delay="200">
            <div class="title">
              頭洲過嶺雙重劃
              <br />四大商圈正核心
            </div>
            <div class="desc">
              最受歡迎的新興住宅區，
              <br />青埔、中壢、平鎮、新屋四大商圈正核心
              <br />食衣住行生活採買，超強機能潛力無窮
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

  .bg-img {
    top: 0;
    bottom: 0;
    height: auto;
  }
}

@media screen and (max-width: 767px) {
  .bg {
    // background-size: 100% 100%;
  }

  .content {
    position: absolute;
    left: calc(100vw * 25 / 375);
    bottom: calc(100vh * 100 / 675);
  }

  .title {
    font-size: 36px;
    font-weight: bold;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.09;
    letter-spacing: normal;
    text-align: left;
    color: #ffffff;
    margin-bottom: 15px;
  }

  .desc {
    font-size: 14px;
    font-weight: bold;
    font-stretch: normal;
    font-style: normal;
    line-height: 1.4;
    letter-spacing: normal;
    text-align: left;
    color: #ffffff;
  }
}
</style>
<script>
// @ is an alias to /src
import { isMobile } from '@/utils'

export default {
  name: 'section2',

  data() {
    return {
      isMobile,
    }
  },

  methods: {},
}
</script>
