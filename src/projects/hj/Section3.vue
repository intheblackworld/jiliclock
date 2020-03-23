<template>
  <div class="section3">
    <div
      v-if="!isMobile"
      class="full-bg"
    >
      <img
        v-lazy="require('./s3/img.jpg')"
        alt=""
        class="left"
      >
<svg v-if="showIcon" class="timg" version="1.1" id="圖層_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
	 viewBox="0 0 346.4 474" style="enable-background:new 0 0 346.4 474;" xml:space="preserve">
  <g id="_x33_">
    <circle class="st0 line6" cx="173.2" cy="173.2" r="173.2"/>
    <text transform="matrix(1 0 0 1 29.93 182.3701)" class="st1 st2 st3">大安區</text>
  </g>
  <line id="_x32_" class="st4 line5" x1="173.2" y1="102.3" x2="173.2" y2="464.7"/>
  <g id="_x31__1_">
    <circle class="st5 line4" cx="173.2" cy="423.9" r="46.2"/>
    <circle class="st6 line3" cx="173.2" cy="292.4" r="46.2"/>
    <circle class="st6 line2" cx="173.2" cy="168.5" r="46.2"/>
    <circle class="st6 line1" cx="173.2" cy="54.7" r="46.2"/>
  </g>
  <text transform="matrix(1 0 0 1 204.36 364.3501)" class="st7 st8 st9 line3-2">10min</text>
  <text transform="matrix(1 0 0 1 206.89 234.3398)" class="st7 st8 st9 line2-2">5min</text>
  <text transform="matrix(1 0 0 1 206.89 116.0698)" class="st7 st8 st9 line1-2">2min</text>
  <text transform="matrix(1 0 0 1 133.13 434.3101)" class="st7 st8 st3 line4-1">南勢角</text>
  <text transform="matrix(1 0 0 1 146.18 302.8599)" class="st7 st8 st3 line3-1">古亭</text>
  <text transform="matrix(1 0 0 1 146.18 178.9399)" class="st7 st8 st3 line2-1">東門</text>
  <text transform="matrix(1 0 0 1 146.18 49.1802)" class="st7 st8 st3 line1-1">忠孝</text>
  <text transform="matrix(1 0 0 1 146.18 80.0298)" class="st7 st8 st3 line1-1">新生</text>
</svg>
      <div class="content">
        <div class="title">
          BEST<br />TRAFFIC
        </div>
        <div class="subtitle">
          10分鐘的美好相遇
        </div>
        <div class="desc">
          4站古亭5站東門，6站忠孝新生7站松江南京，各線匯集，去哪都便利。國道三號、64快速道路聯外交通樞紐，加上新北環狀線多線齊發，無論你想去哪，都一路幸福到家。
        </div>
      </div>
      <img
        v-lazy="require('./s3/logo.png')"
        alt=""
        class="logo"
      >
    </div>
    <div
      v-else
      class="m-bg"
    >
      <img
        v-lazy="require('./s3/mo/img.jpg')"
        alt=""
        class="top"
      >
      <div class="bottom">
        <div class="m-content">
          <div class="title">
            BEST<br />TRAFFIC
          </div>
          <div class="subtitle">
            10分鐘的美好相遇
          </div>
          <div class="desc">
            一分鐘進捷運，加上國道三號、64快速道路、新北環狀線多線齊發，各線匯集，去哪都便利。
          </div>
        </div>
      </div>
<svg v-if="showIcon" class="timg" version="1.1" id="圖層_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
	 viewBox="0 0 346.4 474" style="enable-background:new 0 0 346.4 474;" xml:space="preserve">
  <g id="_x33_">
    <circle class="st0 line6" cx="173.2" cy="173.2" r="173.2"/>
    <text transform="matrix(1 0 0 1 29.93 182.3701)" class="st1 st2 st3">大安區</text>
  </g>
  <line id="_x32_" class="st4 line5" x1="173.2" y1="102.3" x2="173.2" y2="464.7"/>
  <g id="_x31__1_">
    <circle class="st5 line4" cx="173.2" cy="423.9" r="46.2"/>
    <circle class="st6 line3" cx="173.2" cy="292.4" r="46.2"/>
    <circle class="st6 line2" cx="173.2" cy="168.5" r="46.2"/>
    <circle class="st6 line1" cx="173.2" cy="54.7" r="46.2"/>
  </g>
  <text transform="matrix(1 0 0 1 204.36 364.3501)" class="st7 st8 st9 line3-2">10min</text>
  <text transform="matrix(1 0 0 1 206.89 234.3398)" class="st7 st8 st9 line2-2">5min</text>
  <text transform="matrix(1 0 0 1 206.89 116.0698)" class="st7 st8 st9 line1-2">2min</text>
  <text transform="matrix(1 0 0 1 133.13 434.3101)" class="st7 st8 st3 line4-1">南勢角</text>
  <text transform="matrix(1 0 0 1 146.18 302.8599)" class="st7 st8 st3 line3-1">古亭</text>
  <text transform="matrix(1 0 0 1 146.18 178.9399)" class="st7 st8 st3 line2-1">東門</text>
  <text transform="matrix(1 0 0 1 146.18 49.1802)" class="st7 st8 st3 line1-1">忠孝</text>
  <text transform="matrix(1 0 0 1 146.18 80.0298)" class="st7 st8 st3 line1-1">新生</text>
</svg>
      <img
        v-lazy="require('./s3/mo/bglogo.png')"
        alt=""
        class="logo"
        data-aos="fade"
        data-aos-delay="400"
      >
    </div>
  </div>
</template>

<style lang="scss">
.section3{
	.st0{opacity:0;fill:#FFFFFF;enable-background:new;}
	.st1{fill:#112D81;}
	.st2{font-family:"Noto Sans TC", serif;}
	.st3{font-size:26.1px;}
	.st4{fill:none;stroke:#D33645;stroke-width:8;stroke-miterlimit:10;
    stroke-dasharray:363;
    stroke-dashoffset: 363;}
	.st5{fill:#D3364500;stroke:#D33645;stroke-width:8;stroke-miterlimit:10;
    stroke-dasharray:291;
    stroke-dashoffset: 291;}
	.st6{fill:#112D8100;stroke:#D33645;stroke-width:8;stroke-miterlimit:10;
    stroke-dasharray:291;
    stroke-dashoffset: 291;}
	.st7{fill:#FFFFFF;}
	.st8{font-family:"Noto Sans TC", serif;}
	.st9{font-size:23.73px;}
  .line1 {animation: an01 1s linear forwards;}
  .line1-1 {animation: an01-1 1s 0.5s linear forwards;opacity:0;}
  .line1-2 {animation: an01-1 1s 1s linear forwards;opacity:0;}
  .line2 {animation: an02 1s 1s linear forwards;}
  .line2-1 {animation: an01-1 1s 1.5s linear forwards;opacity:0;}
  .line2-2 {animation: an01-1 1s 2s linear forwards;opacity:0;}
  .line3 {animation: an03 1s 2s linear forwards;}
  .line3-1 {animation: an01-1 1s 2s linear forwards;opacity:0;}
  .line3-2 {animation: an01-1 1s 2.5s linear forwards;opacity:0;}
  .line4 {animation: an04 1s 3s linear forwards;}
  .line4-1 {animation: an01-1 1s 3.5s linear forwards;opacity:0;}
  .line5 {animation: an05 1s 4s linear forwards;}
  .line6 {animation: an06 1s 5s linear forwards;}
  @keyframes an01 {
  to { stroke-dashoffset: 0;fill:#112D81FF;}
}
  @keyframes an01-1 {
  to {  opacity:1;}
}
  @keyframes an02 {
  to { stroke-dashoffset: 0;fill:#112D81FF;}
}
  @keyframes an03 {
  to { stroke-dashoffset: 0;fill:#112D81FF;}
}
  @keyframes an04 {
  to { stroke-dashoffset: 0;fill:#D33645FF;}
}
  @keyframes an05 {
  to { stroke-dashoffset: 0}
}
  @keyframes an06 {
  to{opacity:0.2;}
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
  width: size(392);
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
.timg{width:size(350);
  position: absolute;
  top: size(280);
  left:50%;
  margin: 0 0 0 size(540);
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
    height: size-m(670);
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
  }

  .m-img {
    width: 100vw;
    position: absolute;
    right: 0;
    bottom: 0;
  }
  .m-content {
    width: size-m(185);
  }

  .title {
    font-size: size-m(47);
    letter-spacing: 2.23px;
  }

  .subtitle {
    font-size: size-m(15);
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
.timg{width:size-m(150);
  position: absolute;
  top: size-m(410);
  left:56%;
  margin: 0;
  }
}
</style>
<script>
// @ is an alias to /src
import { isMobile } from '@/utils'

export default {
  name: 'section3',
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
