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
                  v-lazy="require('./s2/test_img_2.jpg')"
                  alt=""
                >
              </div>
              <div class="video-content" @click="goVideo('20UCkr8C5j8')">
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
@import '@/assets/style/function.scss';
.bg {
  background-size: cover;
  background-position: center;
  position: relative;
  background-color: #101010;
}

.container {
  width: 1080px;
  height: 100%;
  margin: 0 auto;
  position: relative;
  padding: 40px;
  background: #111;
  box-shadow: 0 0 80px 0 rgba(0, 0, 0, 0.2);
}

.title {
  font-size: 36px;
  color: #ccc;
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
  color: #ccc;
  font-size: 20px;
  cursor: pointer;
}

.video-list {
  width: 75%;

  .list-title {
    font-size: 20px;
    color: #ccc;
    margin-bottom: 24px;
  }

  .video-item {
    width: 100%;
    height: 188px;
    display: flex;
    justify-content: space-between;
    margin-bottom: 20px;
    background: #222;
    // border: 1px solid #eee;
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
    color: #ccc;
    margin-bottom: 20px;
  }

  .video-desc {
    font-size: 16px;
    color: #cecece;
  }

  .video-date {
    position: absolute;
    right: 10px;
    bottom: 10px;
    color: #ccc;
  }
}

.content {
  display: flex;
  justify-content: space-between;
}

.acc-enter {
  width: 25%;
  color: #ccc;
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
  .container {
    width: 100vw;
    padding: 20px;
  }

  .title {
    font-size: size-m(20)
  }

  .tab {
    .item {
      font-size: size-m(16)
    }
  }

  .video-list {
    width: 100%;
    .video-item {
      position: relative;
    }
    .video-avatar {
      width: 100%;
    }
    .video-content {
      position: absolute;
      position: absolute;
      width: 100%;
      height: 100%;
      background:rgba(0, 0, 0, 0.4);
    }

    .video-title {
      font-size: size-m(20);
      color: #fff;
      margin-top: 30px;
    }

    .video-desc {
      font-size: size-m(14);
    }

    .video-date {
      font-size: size-m(14);
    }
  }

  .acc-enter {
    display: none;
  }
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
