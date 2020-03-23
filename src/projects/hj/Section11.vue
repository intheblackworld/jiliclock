<template>
  <div class="section11">
    <div
      v-if="!isMobile"
      class="full-bg"
    >
      <div
      
          class="box"
        data-aos="fade"
        data-aos-delay="200"
      >
      </div>
      <img
        v-lazy="require('./s11/img1.png')"
        alt=""
        class="left"
      >
      <div
        data-aos="fade"
        data-aos-delay="300"
      >
        <img
          v-lazy="require('./s11/11@2x1.png')"
          alt=""
          class="right-img"
          v-scroll-to="{ element: `#contact` }"
        >
      </div>
    </div>
    <div
      v-else
      class="m-bg"
    >
      <img
        v-lazy="require('./s11/mo/img1.png')"
        alt=""
        class="img"
      >
      <div
        data-aos="fade"
        data-aos-delay="300"
      >
        <img
          v-lazy="require('./s11/mo/t1.png')"
          alt=""
          class="img"
        >
      </div>
      <img
        src="./s11/mo/button.png"
        alt=""
        class="btn"
        v-scroll-to="{ element: `#contact` }"
      >
    </div>
  </div>
</template>
<style lang="scss" scoped>
@import '@/assets/style/function.scss';

.full-bg {
  background-image: linear-gradient(to right, #e7380d 0%, #e4006e);
}
.box{
  position: absolute;
  background-color: #112d81;
  width: 100%;
  height: 80%;top: 10%;
  left: 0;
  // background-image: linear-gradient(to right, #e7380d 0%, #e4006e);
}

.left {
  width: auto;
  height: 100vh;
  left: 0;
  right: 0;
  margin: 0 auto;
  position: absolute;
  top: 50%;
  display: block;
  transform: translate(-50%, -50%);
}

.right-img {
  width: auto;
  height: 100vh;
  left: 0;
  right: 0;
  margin: 0 auto;
  position: absolute;
  display: block;
  transform: translateX(50%);
  cursor: pointer;
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
    font-family: GenShinGothic;
    font-size: size(32);
    font-weight: bold;
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
    height: size-m(400);
    position: relative;
  }

  .img {
    width: 100vw;
    height: auto;
    position: absolute;
    top: 0;
    left: 0;
  }

  .btn {
    width: size-m(142);
    position: absolute;
    cursor: pointer;
    right: size-m(40);
    top: size-m(283);
  }
}
</style>
<script>
// @ is an alias to /src
import { isMobile } from '@/utils'

export default {
  name: 'section11',
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
