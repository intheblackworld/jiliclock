<template>
  <div class="section6">
    <div
      v-if="!isMobile"
      class="full-bg"
    >
      <img
        v-lazy="require('./s6/img.jpg')"
        alt=""
        class="left"
      >
<svg v-if="showIcon" class="timg" version="1.1" id="圖層_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
	 viewBox="0 0 544.9 474.8" style="enable-background:new 0 0 544.9 474.8;" xml:space="preserve">
  <path class="st0 an04" d="M399.2,319.5c-41.5,0-75.2,33.6-75.2,75.1s33.6,75.2,75.1,75.2s75.2-33.6,75.2-75.1c0,0,0,0,0,0h70.6"/>
  <path class="st0 an03" d="M403.5,218.1c41.5,0.5,74.8,34.5,74.3,76c-0.5,40.8-33.5,73.8-74.3,74.3"/>
  <path class="st0 an02" d="M403.2,105.1c-0.6,0-1.2,0-1.7,0c-41.5,0.5-74.8,34.5-74.3,76s34.5,74.8,76,74.3"/>
  <path class="st0 an01" d="M0,80.2h327.5c0,0,0,0,0,0c0-41.5,33.7-75.2,75.2-75.2s75.2,33.7,75.2,75.2s-33.7,75.2-75.2,75.2"/>
  <text transform="matrix(1 0 0 1 374.24 403.6802)" class="st1 st2 st3 st4 an08">BEST</text>
  <text transform="matrix(1 0 0 1 355.06 427.3301)" class="st1 st2 st3 st4 an08">STATION</text>
  <text transform="matrix(1 0 0 1 371.38 299.7002)" class="st5 st6 st7 st8 an07">生活</text>
  <text transform="matrix(1 0 0 1 371.38 194.73)" class="st5 st6 st7 st8 an06">娛樂</text>
  <text transform="matrix(1 0 0 1 371.38 79.6499)" class="st5 st6 st7 st8 an05">休憩</text>
</svg>
      <div class="content">
        <div class="title">
          BEST<br />VACATION
        </div>
        <div class="subtitle">
          把各種美好串連在一起
        </div>
        <div class="desc">
          搭捷運去旅行，把各種美好串連在一起。下班後到兩廳院陶冶身心、周末漫步大安森林公園休憩、環狀線直達新板特區接軌時尚，走在休閒娛樂享受最前線，你想得到的，都有。
        </div>
      </div>
      <img
        v-lazy="require('./s6/logo.png')"
        alt=""
        class="logo"
      >
    </div>
    <div
      v-else
      class="m-bg"
    >
      <img
        v-lazy="require('./s6/mo/img.jpg')"
        alt=""
        class="top"
      >
      <div class="bottom">
        <div class="m-content">
          <div class="title">
            BEST<br />VACATION
          </div>
          <div class="subtitle">
            把各種美好串連在一起
          </div>
          <div class="desc">
            搭捷運去旅行，從兩廳院到大安森林公園、新板特區到台師大校園。
            你想得到的休閒娛樂享受，都有。

          </div>
        </div>
      </div>
<svg v-if="showIcon" class="timg" version="1.1" id="圖層_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
	 viewBox="0 0 544.9 474.8" style="enable-background:new 0 0 544.9 474.8;" xml:space="preserve">
  <path class="st0 an04" d="M399.2,319.5c-41.5,0-75.2,33.6-75.2,75.1s33.6,75.2,75.1,75.2s75.2-33.6,75.2-75.1c0,0,0,0,0,0h70.6"/>
  <path class="st0 an03" d="M403.5,218.1c41.5,0.5,74.8,34.5,74.3,76c-0.5,40.8-33.5,73.8-74.3,74.3"/>
  <path class="st0 an02" d="M403.2,105.1c-0.6,0-1.2,0-1.7,0c-41.5,0.5-74.8,34.5-74.3,76s34.5,74.8,76,74.3"/>
  <path class="st0 an01" d="M0,80.2h327.5c0,0,0,0,0,0c0-41.5,33.7-75.2,75.2-75.2s75.2,33.7,75.2,75.2s-33.7,75.2-75.2,75.2"/>
  <text transform="matrix(1 0 0 1 374.24 403.6802)" class="st1 st2 st3 st4 an08">BEST</text>
  <text transform="matrix(1 0 0 1 355.06 427.3301)" class="st1 st2 st3 st4 an08">STATION</text>
  <text transform="matrix(1 0 0 1 371.38 299.7002)" class="st5 st6 st7 st8 an07">生活</text>
  <text transform="matrix(1 0 0 1 371.38 194.73)" class="st5 st6 st7 st8 an06">娛樂</text>
  <text transform="matrix(1 0 0 1 371.38 79.6499)" class="st5 st6 st7 st8 an05">休憩</text>
</svg>
      <img
        v-lazy="require('./s6/mo/bglogo.png')"
        alt=""
        class="logo"
        data-aos="fade"
        data-aos-delay="400"
      >
    </div>
  </div>
</template>
<style lang="scss">
.section6{
	.st0{fill:none;stroke:#D33645;stroke-width:10;stroke-miterlimit:10;}
	.st1{fill:#FFFFFF;}
	.st2{font-family:'Impact';}
	.st3{font-size:24.26px;}
	.st4{letter-spacing:2;}
	.st5{opacity:0.6;fill:#FFFFFF;enable-background:new    ;}
	.st6{font-family:"Noto Sans TC", serif;}
	.st7{font-size:28.45px;}
	.st8{letter-spacing:4;}
	.an01{stroke-dasharray:683;
    stroke-dashoffset:683;
    animation: an01 1s 1.5s linear forwards;
  }
	.an02{stroke-dasharray:240;
    stroke-dashoffset:240;
    animation: an01 0.5s 2s linear forwards;
  }
	.an03{stroke-dasharray:240;
    stroke-dashoffset:240;
    animation: an01 0.5s 2.5s linear forwards;
  }
	.an04{stroke-dasharray:425;
    stroke-dashoffset:425;
    animation: an01 0.5s 3s linear forwards;
  }
  .an05{opacity:0;animation: an02 0.5s 1.5s linear forwards;}
  .an06{opacity:0;animation: an02 0.5s 2s linear forwards;}
  .an07{opacity:0;animation: an02 0.5s 2.5s linear forwards;}
  .an08{opacity:0;animation: an03 0.5s 3s linear forwards;}
  @keyframes an01 {
  to { stroke-dashoffset: 0;}
  }
  @keyframes an02 {
  to{opacity:0.6;}
  }
  @keyframes an03 {
  to{opacity:1;}
  }
}
</style>
<style lang="scss" scoped>
@import '@/assets/style/function.scss';

.full-bg {
  background-color: #112d81;
}

.left {
  width: auto;
  height: size(889);
  left: 0;
  right: 0;
  margin: 0 auto;
  position: absolute;
  top: 50%;
  transform: translate(-50%, -50%);
}

.right-img {
  width: auto;
  height: 100vh;
  left: 0;
  right: 0;
  margin: 0 auto;
  position: absolute;
  transform: translateX(50%);
}

.swiper-fullscreen {
  width: auto;
  height: 100vh;
  img {
    width: auto;
    height: 100%;
  }
}

.content {
  position: absolute;
  width: size(520);
  height: 100vh;
  left: 0;
  right: 0;
  margin: 0 auto;
  transform: translateX(65%);
  top: 25%;
  > div {
    width: 100%;
  }
}

.title {
  opacity: 0.8;
  font-family: Impact;
  font-size: size(111);
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: 0.99;
  letter-spacing: 6.67px;
  text-align: left;
  color: #db364a;
  margin-bottom: size(30);
}

.subtitle {
  font-size: size(35);
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.04;
  letter-spacing: 5.67px;
  text-align: left;
  color: #db364a;
  white-space: nowrap;
  margin-bottom: size(30);
}

.desc {
  font-size: size(15);
  font-weight: 300;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.6;
  letter-spacing: 1.19px;
  text-align: left;
  color: #ffffff;
}

.logo {
  position: absolute;
  width: auto;
  height: 100vh;
  right: 5%;
}
.timg{width:size(550);
  position: absolute;
  top: size(280);
  left:50%;
  margin: 0 0 0 size(335);
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
  .m-bg {
    background-color: #112d81;
    height: size-m(667);
    position: relative;
  }
  .logo {
    width: size-m(185);
    top: size-m(240);
    left: 0;
    right: 0;
    margin: 0 auto;
    position: absolute;
    z-index: 1;
  }
  .top {
    width: size-m(330);
    margin: 0 auto;
  }
  .bottom {
    width: size-m(330);
    margin: size-m(40) auto;
    display: flex;
    position: relative;
    bottom: 20px;
  }

  .m-img {
    width: 100vw;
    position: absolute;
    right: 0;
    bottom: 0px;
  }
  .m-content {
    width: size-m(200);
  }

  .title {
    font-size: size-m(47);
    letter-spacing: 2.23px;
  }

  .subtitle {
    font-size: size-m(15);
    margin-bottom: size-m(20);
  }

  .desc {
    font-size: size-m(12);
  }

  .logo {
    width: 100vw;
    height: auto;
    position: absolute;
    top: auto;
    bottom: 0;
    right: auto;
    left: 0;
    transform: none;
  }
.timg{width:size-m(230);
  position: absolute;
  top: size-m(385);
  left:34%;
  margin: 0;
  }
}
</style>
<script>
// @ is an alias to /src
import { isMobile } from '@/utils'

export default {
  name: 'section6',
  props: ['showIcon'],
  data() {
    return {
      isMobile,
    }
  },

  methods: {},

  mounted() {},

  computed: {},
}
</script>
