<template>
  <div class="bg no-padding-top">
    <Loading :loading="load" />
    <!-- <SideNavigation v-if="isSide" /> -->
    <Navigation />
    <!-- <Indigator :viewIndex="viewIndex" /> -->
    <div class="container">
      <div class="content">
        <div class="main-video">
          <iframe
            :src="`https://www.youtube.com/embed/${video_id}?cc_load_policy=1&enablejsapi=1&modestbranding=1&rel=0&controls=0`"
            frameborder="0"
            allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
          ></iframe>
          <!-- 配置參考 -->
          <!-- https://developers.google.com/youtube/player_parameters?hl=zh-cn#cc_load_policy -->
        </div>
        <div class="from">影片出處：xxx</div>
        <div class="share">
          分享
          <div
            class='line-it-button'
            style='display: none;'
            data-type='share-d'
            data-lang='zh-Hant'
          ></div>
          <div
            class="fb-share-button"
            data-href="https://www.your-domain.com/your-page.html"
            data-layout="button_count"
            data-size="large"
          >
          </div>
        </div>
        <div class="video-list">
          <div class="list-title">【推薦觀看】</div>
          <div
            class="video-item"
            v-for="index in 5"
            :key="`video-${index}`"
          >
            <div
              class="video-avatar"
              @click="goVideo(index)"
            >
              <img
                v-lazy="require('@/projects/clock/s2/test_img_2.jpg')"
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
      </div>
      <div class="side">
        <div class="block">設定鬧鐘</div>
        <div class="block">廣告</div>
        <div class="rank">
          <div class="rank-title">人氣排行</div>
          <div class="rank-list">
            <div class="rank-item" v-for="index in 5" :key="`rank-${index}`">
              <div class="item-index">
                0{{index}}
              </div>
              <div class="item-title">
                激勵影片1
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
@import '@/assets/style/function.scss';
.bg {
  background: #010101;
}
.container {
  width: 1080px;
  height: 100%;
  margin: 0 auto;
  position: relative;
  padding: 120px 20px 40px 0;
  background: #111;
  // box-shadow: 0 0 80px 0 rgba(0, 0, 0, 0.2);
  display: flex;
  justify-content: space-between;
}

.content {
  width: 763px;
}

.side {
  width: 263px;
}

.main-video {
  width: 100%;
  height: 450px;
  iframe {
    width: 100%;
    height: 100%;
  }
}

.from {
  font-size: 18px;
  color: #ccc;
  margin: 20px 0 30px 60px;
  text-align: left;
}

.share {
  font-size: 22px;
  color: green;
}

.video-list {
  width: 100%;
  margin-top: 30px;
  padding-left: 20px;

  .list-title {
    font-size: 20px;
    color: #ccc;
    text-align: left;
    margin-bottom: 24px;
  }

  .video-item {
    width: 90%;
    height: 188px;
    display: flex;
    justify-content: space-between;
    margin-bottom: 20px;
    background: #222;
    margin-left: 10%;
  }

  .video-avatar {
    width: 50%;
    height: 100%;
    overflow: hidden;

    img {
      width: 100%;
      object-fit: cover;
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

.block {
  width: 100%;
  height: 200px;
  line-height: 200px;
  background: #333;
  color: #fff;
  margin-bottom: 25px;
}

.rank {
  .rank-title {
    font-size: 32px;
    color: #a01e1e;
    margin-top: 30px;
    margin-bottom: 30px;
  }

  .rank-list {
    width: 100%;
    padding: 30px 15px 15px;
    background: #333;
    box-shadow: 0 2px 4px rgba(0,0,0,.5);
  }

  .rank-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 35px;
  }

  .item-index {
    font-size: 32px;
    color: #a01e1e;
  }

  .item-title {
    font-size: 16px;
    color: #ccc;
    text-align: left;
  }
}

@media screen and (max-width: 767px) {
  .container {
    width: 100vw;
    padding: 120px 0px 40px 0
  }

  .side {
    display: none;
  }
  .main-video {
    width: 100vw;
    height: size-m(218);
  }

  .from {
    margin: 20px 0 30px 20px
  }
  .list-title {
    width: 90%;
    margin: 20px auto;
  }

  .video-list {
    width: 100%;
    padding-left: 0;
    .video-item {
      position: relative;
      margin: 20px auto;
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
}
</style>

<script>
import Navigation from '@/layouts/Navigation.vue'
import Loading from '@/components/Loading.vue'

export default {
  name: 'Video',
  components: {
    Loading,
    Navigation,
  },
  data() {
    return {
      load: true,
    }
  },
  created() {
    setTimeout(() => {
      this.load = false
    }, 500)
    // window.addEventListener('load', event => {
    //   this.load = false
    // })
  },

  computed: {
    video_id() {
      return this.$route.params.id
    }
  },

  mounted() {
    // window.addEventListener('scroll', this.onScroll, false)
  },
  methods: {},
}
</script>
