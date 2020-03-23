<template>
  <div class="section6">
    <div class="bg">
      <div v-if="!isMobile">
        <img src="./s6/bg.jpg" alt class="bg-img" />
        <div class="content" data-aos="fade-right" data-aos-delay="200">
          <div class="title">競速生活，無與倫比</div>
          <div class="desc">
            2分鐘直上台66線快速道，縱橫東西無極限
            <br />中山高5分/北二高12分，聯外城市超級快
          </div>
        </div>
      </div>
      <div v-else>
        <div class>
          <!-- <img src="./s3/mo/1.jpg" alt class="img" data-aos="zoom-in" data-aos-delay="200" /> -->
          <img src="./s6/mo/bg.jpg" alt class="bg-img" />
          <div class="content" data-aos="fade-down" data-aos-delay="200">
            <div class="title">競速生活，無與倫比</div>
            <div class="desc">
              2分鐘直上台66線快速道，縱橫東西無極限
              <br />中山高5分/北二高12分，聯外城市超級快
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
  left: calc(100vw * 108 / 1920);
  top: calc(100vh * 550 / 940);
}

.title {
  font-size: calc(100vw * 72.5 / 1920);
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
  font-size: calc(100vw * 27 / 1920);
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
    top: calc(100vh * 750 / 940);
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
    top: calc(100vh * 380 / 940);
  }
}

@media screen and (max-width: 767px) {
  .bg {
    // background-size: 100% 100%;
  }

  .content {
    position: absolute;
    left: calc(100vh * 25 / 675);
    right: auto;
    top: auto;
    bottom: calc(100vh * 0 / 675);
  }

  .title {
    font-size: calc(100vw * 36 / 375);
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
    font-size: calc(100vw * 14 / 375);
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
  name: 'section6',

  data() {
    return {
      isMobile,
    }
  },

  methods: {},
}
</script>
