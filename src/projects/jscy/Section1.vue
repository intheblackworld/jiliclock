<template>
  <div class="section1">
    <div class="bg">
      <div v-if="!isMobile">
        <img src="./s1/bg.png" alt class="bg-img absolute" data-aos="fade" data-aos-delay="600" />
        <img src="./s1/cloud.png" alt class="bg-img absolute cloud" />
        <img src="./s1/bg1.png" alt class="bg-img relative" data-aos="fade" data-aos-delay="600" />
        <img src="./s1/bg2.jpg" alt class="bg-img relative" data-aos="fade" data-aos-delay="600" />
        <img
          src="./s1/1.png"
          alt="堅山謙仰 THE UPPERHOME"
          :class="['bg-img', isAbsolute ? 'absolute aos-init aos-animate' : 'aos-init aos-animate']"
          data-aos="fade"
          data-aos-delay="800"
        />
        <img
          src="./s1/2.png"
          alt="超越ARTDECO 奢華／坐擁高雄 美術館無價 LIFE IS ABOUT CREATING YOURSELF."
          :class="['bg-img', isAbsolute ? 'absolute aos-init aos-animate' : 'aos-init aos-animate']"
          data-aos="fade"
          data-aos-delay="1000"
        />
      </div>
      <div v-else>
        <img src="./s1/mo/bg.jpg" alt class="bg-img" data-aos="fade" data-aos-delay="200" />
        <img src="./s1/mo/雲.png" alt class="bg-img cloud" />
        <img
          src="./s1/mo/2.png"
          alt="堅山謙仰 THE UPPERHOME"
          class="bg-img"
          data-aos="fade-down"
          data-aos-delay="600"
        />
        <img
          src="./s1/mo/3.png"
          alt="超越ARTDECO 奢華／坐擁高雄"
          class="bg-img"
          data-aos="fade-down"
          data-aos-delay="800"
        />
        <img
          src="./s1/mo/4.png"
          alt="美術館無價 LIFE IS ABOUT CREATING YOURSELF."
          class="bg-img"
          data-aos="fade-down"
          data-aos-delay="1000"
        />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.bg {
  background-size: cover;
  position: relative;
}
.bg-img {
  width: 100vw;
  position: fixed;
  top: 0;
  left: 0;
  height: auto;
  display: block;
  // height: 100%;
  object-fit: cover;

  &:nth-child(1) {
    position: relative;
  }

  &.relative {
    position: relative !important;
  }

  &.absolute {
    position: absolute !important;
  }
}

.cloud {
  width: 100vw;
  left: 50%;
  animation: cloud 20s linear infinite;
}

@keyframes cloud {
  0% {
    transform: translate(-100%, 0%);
  }

  100% {
    transform: translate(0%, -100%);
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

  .bg-img {
    position: absolute;
  }

  .cloud {
    width: 200vw;
    animation: cloud 35s linear infinite;
  }

  @keyframes cloud {
    0% {
      transform: translate(-50%, 0%);
    }

    100% {
      transform: translate(0%, -50%);
    }
  }
}
</style>
<script>
// @ is an alias to /src
import { isMobile } from '@/utils'

export default {
  name: 'section1',

  data() {
    return {
      isMobile,
      isAbsolute: false,
    }
  },

  methods: {},

  mounted() {
    // let prevScrollpos = window.pageYOffset
    window.onscroll = () => {
      const currentScrollPos = window.pageYOffset
      if (currentScrollPos > window.innerHeight * 1.5) {
        this.isAbsolute = true
      } else {
        this.isAbsolute = false
        // this.isAbsolute = false
        // console.log(this.isAbsolute)
      }
      // prevScrollpos = currentScrollPos
    }
  },
}
</script>
