<template>
  <div class="section3">
    <div class="bg">
      <div v-if="!isMobile">
        <img src="./s3/bg.jpg" alt class="bg-img" />
        <div class="content" data-aos="fade-down" data-aos-delay="200">
          <div class="title">千坪大公園，就在家門口</div>
          <div class="desc">步行1分鐘，就到頭洲最大公園綠地 等同買下1,684坪大中庭</div>
        </div>
      </div>
      <div v-else>
        <div class>
          <!-- <img src="./s3/mo/1.jpg" alt class="img" data-aos="zoom-in" data-aos-delay="200" /> -->
          <img src="./s3/mo/bg.jpg" alt class="bg-img" />
          <div class="content" data-aos="fade-down" data-aos-delay="200">
            <div class="title">
              千坪大公園
              <br />就在家門口
            </div>
            <div class="desc">
              步行1分鐘，就到頭洲最大公園綠地
              <br />等同買下1,684坪大中庭
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
  left: calc(100vw * 290 / 1920);
  top: calc(100vh * 116 / 940);
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
    left: calc(100vw * 30 / 375);
    top: calc(100vh * 130 / 675);
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
  name: 'section3',

  data() {
    return {
      isMobile,
    }
  },

  methods: {},
}
</script>
