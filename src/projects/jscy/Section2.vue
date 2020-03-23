<template>
  <div class="section2">
    <div class="bg">
      <div v-if="!isMobile">
        <img src="./s2/0.png" alt="家 就是一座美術館" class="bg-img" />
        <img src="./s2/1.png" alt="我們以打磨一座「藝術精品」精神，創作【堅山謙仰】" class="bg-img" data-aos="zoom-in" data-aos-delay="800" />
        <img src="./s2/2.png" alt="將所有美好事物融入建築細節，讓建築成為一座私人美術館。" class="bg-img" data-aos="zoom-in" data-aos-delay="600" />
      </div>
      <div v-else>
        <div class="">
          <img src="./s2/mo/0.png" alt class="img" data-aos="zoom-in" data-aos-delay="600" />
          <img src="./s2/mo/1.jpg" alt class="img" data-aos="zoom-in" data-aos-delay="800" />
          <h3 class="title">家 就是一座美術館</h3>
          <div class="desc">
            我們以打磨一座「藝術精品」精神，創作【堅山謙仰】
            <br />將所有美好事物融入建築細節，讓建築成為一座私人美術館。
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
    background-size: 100% 100%;
  }

  .img {
    width: 50%;
    height: auto;
  }

  .title {
    margin-top: 67px;
    font-size: 25px;
    font-weight: 600;
    font-style: normal;
    font-stretch: normal;
    line-height: 1.2;
    letter-spacing: 2.5px;
    text-align: center;
    color: #000000;
    margin-bottom: 20px;
  }

  .desc {
    font-size: 14px;
    font-weight: 300;
    font-style: normal;
    font-stretch: normal;
    line-height: 1.89;
    letter-spacing: -.4px;
    text-align: center;
    color: #594a42;
    margin-bottom: 58px;
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
