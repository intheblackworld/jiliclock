<template>
  <div class="section7">
    <div
      v-if="!isMobile"
      class="full-bg"
    >
      <img
        v-lazy="require('./s7/img.jpg')"
        alt=""
        class="left"
      >
<svg v-if="showIcon" class="timg" version="1.1" id="圖層_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
	 viewBox="0 0 149.5 261.4" style="enable-background:new 0 0 149.5 261.4;" xml:space="preserve">
<polyline class="st0 an01" points="129.9,5 5.1,5 5.1,256.4 48,256.4 48,185.8 73.6,185.8 73.6,144.9 48,144.9 48,47.9 124.9,47.9 
	124.9,5 "/>
<polyline class="st0 an02" points="70.4,256.4 144.5,256.4 144.5,77.7 78.7,77.7 78.7,120.6 101.6,120.6 101.6,215.4 75.4,215.4 
	75.4,256.4 "/>
</svg>
      <div class="content">
        <div class="title">
          BEST<span>永泰祥機構</span><br />ARCHITECTURE
        </div>
        <div class="subtitle">
          焠鍊經典 打造永恆
        </div>
        <div class="desc">
          永泰祥開發秉承前瞻膽識與誠信態度，不惜成本、專注為菁英層峰在精華地段鑄造精品豪宅，讓家不僅是遮風擋雨的溫暖居所，更是一種珍藏、一份至寶，代表主人無可取代的風格品味。
        </div>
      </div>
      <img
        v-lazy="require('./s7/logo.png')"
        alt=""
        class="logo"
      >
    </div>
    <div
      v-else
      class="m-bg"
    >
      <img
        v-lazy="require('./s7/mo/img.jpg')"
        alt=""
        class="top"
      >
      <div class="bottom">
        <div class="m-content">
          <div class="title">
            BEST<span>永泰祥機構</span><br />ARCHITECTURE
          </div>
          <div class="subtitle">
            焠鍊經典 打造永恆
          </div>
          <div class="desc">
            永泰祥開發秉承前瞻膽識與誠信態度，專注為菁英層峰在精華地段鑄造精品豪宅，讓家成為一種珍藏、一份至寶。
          </div>
        </div>
      </div>
<svg v-if="showIcon" class="timg" version="1.1" id="圖層_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
	 viewBox="0 0 149.5 261.4" style="enable-background:new 0 0 149.5 261.4;" xml:space="preserve">
<polygon class="st0" points="124.9,47.9 124.9,5 5.1,5 5.1,144.9 5,144.9 5,185.8 5.1,185.8 5.1,255.5 48,255.5 48,185.8 
	73.6,185.8 73.6,144.9 48,144.9 48,47.9 "/>
<polygon class="st0" points="78.7,77.7 78.7,120.6 101.6,120.6 101.6,215.4 75.4,215.4 75.4,256.3 101.6,256.3 101.6,256.4 
	144.5,256.4 144.5,77.7 "/>
</svg>
      <img
        v-lazy="require('./s7/mo/bglogo.png')"
        alt=""
        class="logo"
        data-aos="fade"
        data-aos-delay="400"
      >
    </div>
  </div>
</template>
<style lang="scss">
.section7{
	.st0{fill:none;stroke:#D33645;stroke-width:10;stroke-miterlimit:10;}
	.an01{stroke-dasharray:810;
    stroke-dashoffset:810;
   animation: an01 1.5s 1.5s linear forwards;
  }
	.an02{stroke-dasharray:550;
    stroke-dashoffset:550;
  animation: an01 1s 1.5s linear forwards;
  }
  @keyframes an01 {
  to { stroke-dashoffset: 0;}
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
  height: 100vh;
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

  span {
    opacity: 0.5;
    font-size: size(32);
    font-weight: 500;
    font-stretch: normal;
    font-style: normal;
    line-height: 1;
    letter-spacing: 5.47px;
    text-align: left;
    color: #ffffff;
    transform: translateY(-5px);
    display: inline-block;
  }
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
  width: size(520);
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

.timg{width:size(150);
  position: absolute;
  top: size(560);
  left:50%;
  margin: 0 0 0 size(680);
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
    width: size-m(317);
  }

  .title {
    font-size: size-m(47);
    letter-spacing: 2.23px;
    span {
      font-size: size-m(14);
    }
  }

  .subtitle {
    font-size: size-m(15);
    margin-bottom: size-m(20);
  }

  .desc {
    width: size-m(230);
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
.timg{width:size-m(60);
  position: absolute;
  top: size-m(505);
  left:72%;
  margin: 0;
  }
}
</style>
<script>
// @ is an alias to /src
import { isMobile } from '@/utils'

export default {
  name: 'section7',
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
