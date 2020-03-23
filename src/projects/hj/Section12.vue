<template>
  <div class="section12">
    <div
      v-if="!isMobile"
      class="full-bg"
    >
      <img
        v-lazy="require('./s12/bg.png')"
        alt=""
        class="bg-img"
      >
      <img
        v-lazy="require('./s12/t.png')"
        alt=""
        class="left"
      >
      <div
        data-aos="fade"
        data-aos-delay="300"
      >
        <img
          v-lazy="require('./s12/img1.png')"
          alt=""
          class="right-img"
        >
        <img
          v-lazy="require('./s12/img2.png')"
          alt=""
          class="right-img move"
        >
        <img
          v-lazy="require('./s12/img3.png')"
          alt=""
          class="right-img move"
        >
        <img
          v-lazy="require('./s12/img4.png')"
          alt=""
          class="right-img move"
        >
      </div>
    </div>
    <div
      v-else
      class="m-bg"
    >
      <img
        v-lazy="require('./s12/mo/bg.png')"
        alt=""
        class="img"
      >
      <div
        data-aos="fade"
        data-aos-delay="300"
      >
        <img
          v-lazy="require('./s12/mo/t.png')"
          alt=""
          class="img"
        >
        <img
          v-lazy="require('./s12/mo/img1.png')"
          alt=""
          class="img img-b"
        >
        <img
          v-lazy="require('./s12/mo/img2.png')"
          alt=""
          class="img img-b move"
        >
        <img
          v-lazy="require('./s12/mo/img3.png')"
          alt=""
          class="img img-b move"
        >
        <img
          v-lazy="require('./s12/mo/img4.png')"
          alt=""
          class="img img-b move"
        >
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
@import '@/assets/style/function.scss';

.full-bg {
  background-image: linear-gradient(to right, #e7380d 0%, #e4006e);
}

.bg-img {
  width: 100vw;
  height: 100vh;
  position: absolute;
  left: 0;
  top: 0;
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

.move {
  animation: updown 1.5s .2s ease-in-out infinite alternate;
  &:nth-child(2) {
    animation: updown 1.5s .2s ease-in-out infinite alternate;
  }

  &:nth-child(3) {
    animation: updown 1.5s .5s ease-in-out infinite alternate;
  }

  &:nth-child(4) {
    animation: updown 1.5s .3s ease-in-out infinite alternate;
  }
}

@keyframes updown {
  from {
    margin-top: -30px;
  }
  to {
    margin-top: 0px;
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
}

@media screen and (max-width: 767px) {
  .m-bg {
    background-image: linear-gradient(to top, #e8380d 104%, #e4006e -44%);
    height: size-m(603);
    position: relative;
  }

  .img {
    width: 100vw;
    height: auto;
    position: absolute;
    top: 0;
    left: 0;
  }

  .img-b {
    top: size-m(185);
  }

  @keyframes updown {
  from {
    margin-top: -15px;
  }
  to {
    margin-top: 0px;
  }
}
}
</style>
<script>
// @ is an alias to /src
import { isMobile } from '@/utils'

export default {
  name: 'section12',
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
