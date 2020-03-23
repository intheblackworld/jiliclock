<template>
  <div class="section1">
    <div class="bg">
      <img
        v-lazy="require('./s1/bg.png')"
        alt
        class="bg-img"
      />
      <div class="container">
        <div class="content">
          <div class="title">
            堅持夢想 不要放棄
          </div>
          <div class="subtitle">
            每天早上 重新喚醒你內心的野獸
          </div>
          <div class="desc">
            It's Not Over, Until I win
          </div>
        </div>
        <div class="content-btn">
          <div class="btn">設定鬧鐘</div>
          <div class="btn">觀看影片</div>
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
@import '@/assets/style/function.scss';
.bg {
  background-size: cover;
  background-position: center;
  position: relative;
  overflow: hidden;
  height: 100vh;
  background-image: #000;
}
.bg-img {
  width: 100vw;
  height: 100vh;
  position: absolute;
  top: 0;
  left: 0;
  display: block;
  object-fit: cover;
}

.container {
  width: 1080px;
  height: 100%;
  margin: 0 auto;
  position: relative;
  display: flex;
  justify-content: space-between;
}

.content {
  position: relative;
  width: 450px;
  top: 20%;
}

.title {
  font-size: 48px;
  color: #fff;
  letter-spacing: 6px;
  font-weight: 900;
  margin-bottom: size(30);
  text-shadow: 0 3px #000;
  text-align: right;
}

.subtitle {
  font-size: 28px;
  color: #fff;
  letter-spacing: 3px;
  margin-bottom: size(50);
  font-weight: 600;
  text-shadow: 0 1px #000;
  text-align: right;
}

.desc {
  font-size: 20px;
  color: #fff;
  letter-spacing: 2px;
  font-style: italic;
  text-align: right;
}

.content-btn {
  width: 50%;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.btn {
  width: 240px;
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
  background-color: transparent;
  font-size: 30px;
  box-shadow: 0 0 0 3px #fff;
  margin-top: 30px;
  cursor: pointer;
  transition: all 0.4s;

  &:hover {
    color: #333;
    background-color: #fff;
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
    // height: 100vh;
  }
  .container {
    width: 100vw;
    display: block;
  }

  .content {
    width: 90vw;
    margin: 0 auto;
  }

  .content-btn {
    width: 100%;
    position: relative;
    top: 50%;
    display: block;
  }

  .btn {
    width: 50vw;
    margin: 20px auto;
  }

  .title {
    font-size: size-m(32);
    text-align: left;
    margin-bottom: 20px;
  }

  .subtitle {
    font-size: size-m(19);
    text-align: left;
    margin-bottom: 20px;
  }

  .desc {
    font-size: size-m(15);
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

  mounted() {},

  computed: {},
}
</script>
