<template>
  <div class="section1">
    <div class="bg">
      <div v-if="!isMobile">
        <!-- <img src="./s1/bg1.png" alt class="bg-img relative" data-aos="fade" data-aos-delay="600" /> -->
        <img src="./s1/bg.jpg" alt class="bg-img" />
        <img src="./s1/b.png" alt="合遠建築 OASIS CITY" class="bg-img b" />
        <img src="./s1/bear.gif" alt class="bear" data-aos="fade-right" data-aos-delay="0" />
        <img src="./s1/t.png" alt="608萬起 市心3房含平面車位" class="bg-img t" data-aos="fade-left" data-aos-delay="200" />
        <img src="./s1/title.png" alt="在市心 發現新綠洲 都心綠生活，坐擁悠閒與便利" class="bg-img title" data-aos="fade-left" data-aos-delay="400" />
        <div
          class="number"
          data-aos-id="ani-number"
          data-aos="fade"
          data-aos-offset="50"
          data-aos-delay="600"
          data-aos-duration="500"
          data-aos-mirror="true"
          data-aos-once="false"
        >{{animatedNumber}}</div>
      </div>
      <div v-else>
        <img src="./s1/mo/bg.jpg" alt class="bg-img" />
        <img src="./s1/mo/b.png" alt="合遠建築 OASIS CITY" class="bg-img b" />
        <img src="./s1/mo/bear.gif" alt class="bear" data-aos="fade-right" data-aos-delay="0" />
        <img src="./s1/mo/t.png" alt="608萬起 市心3房含平面車位" class="bg-img t" data-aos="fade-left" data-aos-delay="200" />
        <img src="./s1/mo/title.png" alt="在市心 發現新綠洲 都心綠生活，坐擁悠閒與便利" class="bg-img title" data-aos="fade-left" data-aos-delay="400" />
        <div
          class="number"
          data-aos-id="ani-number"
          data-aos="fade"
          data-aos-offset="50"
          data-aos-delay="600"
          data-aos-duration="500"
          data-aos-mirror="true"
          data-aos-once="false"
        >{{animatedNumber}}</div>
      </div>
    </div>
    <div class="bg">
      <div v-if="!isMobile">
        <!-- <img src="./s1/bg1.png" alt class="bg-img relative" data-aos="fade" data-aos-delay="600" /> -->
        <img src="./s1/bg_02.jpg" alt class="bg-img" />
        <iframe ref="iframe" src="https://www.facebook.com/plugins/video.php?href=https%3A%2F%2Fwww.facebook.com%2F295304711374675%2Fvideos%2F2508860709333921%2F&show_text=0" style="border:none;overflow:hidden" scrolling="no" frameborder="0" allowTransparency="true" allowFullScreen="true"></iframe>
      </div>
      <div v-else>
        <img src="./s1/mo/bg_02.jpg" alt class="bg-img" />
        <iframe ref="iframe" src="https://www.facebook.com/plugins/video.php?href=https%3A%2F%2Fwww.facebook.com%2F295304711374675%2Fvideos%2F2508860709333921%2F&show_text=0" width="100%" height="auto" style="border:none;overflow:hidden" scrolling="no" frameborder="0" allowTransparency="true" allowFullScreen="true"></iframe>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.bg {
  background-size: cover;
  background-position: center;
  position: relative;
  overflow: hidden;
  position: relative;
}

iframe {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  left: 0;
  right: 0;
  margin: 0 auto;
  width: calc(100vw * 1440 / 1920);
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

.b {
  top: auto;
  bottom: 0;
}
.bear {
  left: 0;
  position: absolute;
  bottom: 0;
  width: calc(100vw * 442 / 1920);
}

.title,
.t {
  top: 20%;
}

.number {
  font-size: calc(100vw * 215.8 / 1920);
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: 1.2;
  letter-spacing: -4.32px;
  text-align: center;
  color: #e8db00;
  display: block;
  position: absolute;
  left: 30%;
  top: calc(100% * 540 / 1010);
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
  .bg {
  }

  .title,
  .t {
    top: 0;
  }

  .bear {
    width: calc(100vw * 160 / 375);
    bottom: calc(100% * 66 / 675);
  }

  .number {
    font-size: calc(100vw * 80 / 375);
    left: calc(100% * 20 / 375);
    top: auto;
    bottom: calc(100% * 270 / 675);
  }

  iframe {
    width: 100%;
  }
}
</style>
<script>
// @ is an alias to /src
import { isMobile } from '@/utils'
import { TweenLite } from 'gsap'

export default {
  name: 'section1',

  data() {
    return {
      isMobile,
      tweenedNumber: 0,
    }
  },

  methods: {},

  // created() {
  //   if (this.isMobile) {
      
  //   }
  // },

  mounted() {
    document.addEventListener('aos:in:ani-number', ({ detail }) => {
      TweenLite.to(this.$data, 1.2, { tweenedNumber: 608 })
    })

    document.addEventListener('aos:out:ani-number', ({ detail }) => {
      TweenLite.to(this.$data, 1.2, { tweenedNumber: 608 })
    })
    if (this.isMobile) {
      this.$refs.iframe.height = window.innerWidth * (210 / 375)
    } else {
      this.$refs.iframe.height = window.innerWidth * (1440 / 1920) * (807 / 1440)
    }
  },

  computed: {
    animatedNumber: function() {
      return this.tweenedNumber.toFixed(0)
    },
  },
}
</script>
