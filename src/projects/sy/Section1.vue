<template>
  <div class="section1">
    <div class="bg">
      <div class="star comet"></div>
      <div>
        <!-- <img src="./s1/bg1.png" alt class="bg-img relative" data-aos="fade" data-aos-delay="600" /> -->
        <img
          src="./s1/p.jpg"
          alt
          class="bg-img fullscreen"
          data-aos="zoom-out"
          data-aos-duration="3000"
          data-aos-delay="800"
        />
        <div class="content">
          <img src="./s1/1.png" alt="璽園" class="img1" />
          <img src="./s1/2.png" alt="新莊第一名宅  熱銷限量收藏" class="img2" />
          <img src="./s1/3.png" alt="市中心最後一塊千坪美地 千坪基地 x 地標建築 x 制震宅" class="img3" />
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss">
.star {
  width: 3px;
  height: 3px;
  border-radius: 50%;
  opacity: 0.5;
  position: absolute;
  background-color: rgba(255, 255, 220, 0.2);
  box-shadow: 0 0 40px 0 rgba(255, 255, 220, 0.2), 0 0 20px 0 #ffffff;
  animation: glow 5s infinite;
}

/*  小星*/
.star--medium {
  width: 300px;
  height: 300px;
  box-shadow: 0 0 40px 0 rgba(255, 255, 220, 0.3), 0 0 20px 0 #ffffff,
    inset 0 0 4px #ffffff;
}

/*  大星 */
.star--big {
  width: 300px;
  height: 300px;
  box-shadow: 0 0 40px 0 rgba(255, 255, 220, 0.2), 0 0 20px 0 #ffffff,
    inset 0 0 4px #ffffff;
}

@keyframes glow {
  0% {
    opacity: 0.5;
  }
  50% {
    opacity: 0.2;
  }
  100% {
    opacity: 0.5;
  }
}
</style>
<style lang="scss" scoped>
.bg {
  background-size: cover;
  background-position: center;
  position: relative;
  overflow: hidden;
  position: relative;
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
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);

  img {
    display: block;
    margin: 0 auto;
    margin-bottom: 30px;
  }

  .img1 {
    width: 461px;
  }

  .img2 {
    width: 496px;
  }

  .img3 {
    width: 412px;
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
  .bg {
  }

  .content {
    img {
      display: block;
      margin: 0 auto;
      margin-bottom: 10px;
    }

    .img1 {
      width: calc(100vw * 0.9 * 461 / 496);
    }

    .img2 {
      width: calc(100vw * 0.9 * 496 / 496);
    }

    .img3 {
      width: calc(100vw * 0.9 * 412 / 496);
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
    }
  },

  methods: {},

  mounted() {
    const wH = window.innerHeight
    const wW = window.innerWidth

    const generateStars = n => {
      for (let i = 0; i < n; i++) {
        const div = document.createElement('div')
        div.className =
          i % 30 == 0
            ? 'star star--big'
            : i % 100 == 0
            ? 'star star--medium'
            : 'star'
        // random everywhere!
        //2000是數度
        div.setAttribute(
          'style',
          `top:${Math.round(Math.random() * wH)}px;left:${Math.round(
            Math.random() * wW,
          )}px;animation-duration:${Math.round(Math.random() * 2000) +
            2000}ms;animation-delay:${Math.round(Math.random() * 2000)}ms;`,
        )
        document.querySelector('.bg').appendChild(div)
      }
    }
    /* 數量 */
    generateStars(this.isMobile ? 50 : 150)
  },
}
</script>
