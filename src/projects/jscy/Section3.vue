<template>
  <div class="section2">
    <div class="bg">
      <div v-if="!isMobile">
        <img
          src="./s3/0.png"
          alt="寬敞舒適永久棟距 視野無遮蔽 臨路退縮8米，增加緩衝空間及人行步道，更與美術館區域內唯一40米青海路連結，棟距最寬敞舒適。"
          class="bg-img"
        />
        <img
          src="./s3/1.png"
          alt="基地後方謙退30米及12米，31%低建蔽率規劃，讓棟距開闊，氣勢更顯宏偉，並規劃水景花園植栽增添綠意。"
          class="bg-img"
          data-aos="zoom-in"
          data-aos-delay="800"
        />
      </div>
      <div v-else>
        <div class="">
          <img src="./s3/mo/1.jpg" alt class="img" data-aos="zoom-in" data-aos-delay="600" />
          <h3 class="title">
            寬敞舒適永久棟距
            <br />視野無遮蔽
          </h3>
          <div class="desc">
            臨路退縮8米，增加緩衝空間及人行步道，更與美術館區域內唯一40米青海路連結，棟距最寬敞舒適。
            <br />
            <br />
            基地後方謙退30米及12米，31%低建蔽率規劃，讓棟距開闊，氣勢更顯宏偉，並規劃水景花園植栽增添綠意。
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
    width: 100vw;
  }

  .title {
    width: 285px;
    margin: 0 auto;
    margin-top: 44px;
    font-size: 25px;
    font-weight: 600;
    font-style: normal;
    font-stretch: normal;
    line-height: 1.4;
    letter-spacing: 2.5px;
    text-align: left;
    color: #000000;
    margin-bottom: 23px;
  }

  .desc {
    font-size: 14px;
    font-weight: 300;
    font-style: normal;
    font-stretch: normal;
    line-height: 1.71;
    letter-spacing: 1.5px;
    text-align: justify;
    color: #000000;
    width: 285px;
    margin: 0 auto;
    margin-bottom: 75px;
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
