<template>
  <div class="section2">
    <div class="bg">
      <div class="container">
        <div class="title">你想要</div>
        <div class="tab">
          <div class="item">開始早起</div>
          <div class="item">提高業績</div>
          <div class="item">克服拖延</div>
          <div class="item">突破困境</div>
        </div>
        <div class="content">
          <div class="video-list">
            <div class="list-title">早起系列</div>
            <div
              class="video-item"
              v-for="index in 5"
              :key="`video-${index}`"
            >
              <div
                class="video-avatar"
                @click="goVideo('20UCkr8C5j8')"
              >
                <img
                  v-lazy="require('./s2/test_img_2.jpeg')"
                  alt=""
                >
              </div>
              <div class="video-content">
                <div class="video-title">贏家 - 最激勵影片</div>
                <div class="video-desc">xxxxxx....</div>
                <div class="video-date">2020-03-22</div>
              </div>
            </div>
          </div>
          <div class="acc-enter">
            設定鬧鐘
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.bg {
  background-size: cover;
  background-position: center;
  position: relative;
  background-color: #fff;
}

.container {
  width: 1080px;
  height: 100%;
  margin: 0 auto;
  position: relative;
  padding: 40px;
  background: #fff;
  box-shadow: 0 0 80px 0 rgba(0, 0, 0, 0.2);
}

.title {
  font-size: 36px;
  color: #333;
  text-align: center;
  margin-bottom: 30px;
}

.tab {
  width: 100%;
  height: 45px;
  border-bottom: 2px solid #880000;
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin-bottom: 30px;
}

.item {
  color: #333;
  font-size: 20px;
  cursor: pointer;
}

.video-list {
  width: 75%;

  .list-title {
    font-size: 20px;
    color: #333;
    margin-bottom: 24px;
  }

  .video-item {
    width: 100%;
    height: 188px;
    display: flex;
    justify-content: space-between;
    margin-bottom: 20px;
    border: 1px solid #ccc;
  }

  .video-avatar {
    width: 50%;
    height: 100%;
    overflow: hidden;
    cursor: pointer;

    img {
      width: 100%;
      object-fit: cover;
      transition: transform .3s;
    }

    &:hover {
      img {
        transform: scale(1.1);
      }
    }
  }
  .video-content {
    width: 50%;
    position: relative;
    padding-top: 15px;
  }

  .video-title {
    font-size: 20px;
    color: #333;
    margin-bottom: 20px;
  }

  .video-desc {
    font-size: 16px;
    color: #666;
  }

  .video-date {
    position: absolute;
    right: 10px;
    bottom: 10px;
  }
}

.content {
  display: flex;
  justify-content: space-between;
}

.acc-enter {
  width: 25%;
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

  methods: {
    goVideo(id) {
      this.$router.push({ name: 'video', params: { id } })
    },
  },

  mounted() {},

  computed: {},
}
</script>
