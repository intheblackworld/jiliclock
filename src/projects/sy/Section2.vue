<template>
  <div class="section2">
    <div class="bg fullscreen">
      <div v-if="!isMobile">
        <div class="left">
          <div class="content">
            <div class="title" data-aos="fade-right" data-aos-delay="600">新莊第一名宅</div>
            <div class="subtitle" data-aos="fade-right" data-aos-delay="700">GRAND MANSION</div>
            <div class="desc" data-aos="fade-right" data-aos-delay="800">
              世代大團圓，在地指名地標建築
              <br />新一代豪宅語彙，有著相同的建築鋒芒
              <br />凌空拔高23層安全制震地標建築，現代俐落立面，從璽園得到見證。
            </div>
          </div>
          <div class="imglist">
            <img src="./s2/1.jpg" alt="璽園" class="img" data-aos="fade-up" data-aos-delay="1000" />
            <img src="./s2/2.jpg" alt="璽園" class="img" data-aos="fade-up" data-aos-delay="900" />
            <img src="./s2/3.jpg" alt="璽園" class="img" data-aos="fade-up" data-aos-delay="800" />
            <img src="./s2/4.jpg" alt="璽園" class="img" data-aos="fade-up" data-aos-delay="700" />
          </div>
        </div>
        <div class="right">
          <img src="./s2/5.jpg" alt="璽園" class="img" data-aos="fade-up" data-aos-delay="600" />
        </div>
      </div>
      <div v-else>
        <div class="m-content">
          <div class="title" data-aos="fade-right" data-aos-delay="600">新莊第一名宅</div>
          <div class="subtitle" data-aos="fade-right" data-aos-delay="800">GRAND MANSION</div>
          <div class="desc" data-aos="fade-right" data-aos-delay="1000">
            世代大團圓，在地指名地標建築
            <br />新一代豪宅語彙，有著相同的建築鋒芒
            <br />凌空拔高23層安全制震地標建築，現代俐落立面，從璽園得到見證。
          </div>
        </div>
        <img src="./s2/5.jpg" alt="璽園" class="imgb" data-aos="fade-down" data-aos-delay="400" />
        <div class="imgmlist">
          <img src="./s2/1.jpg" alt="璽園" class="img" data-aos="fade-down" data-aos-delay="600" />
          <img src="./s2/2.jpg" alt="璽園" class="img" data-aos="fade-down" data-aos-delay="700" />
          <img src="./s2/3.jpg" alt="璽園" class="img" data-aos="fade-down" data-aos-delay="800" />
          <img src="./s2/4.jpg" alt="璽園" class="img" data-aos="fade-down" data-aos-delay="900" />
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.bg {
  background-size: cover;
  position: relative;
  overflow: hidden;

  > div {
    display: flex;
  }
}

.left {
  width: 57.2vw;
  position: relative;
  background: #fff;
}

.content {
  margin-top: 11%;
  > div {
    width: calc(100% * 790 / 1100);
    margin: 0 auto;
  }

  .title {
    font-size: calc(100vw * (58 / 1920));
    font-weight: normal;
    font-style: normal;
    font-stretch: normal;
    line-height: 0.66;
    letter-spacing: normal;
    text-align: left;
    color: #507913;
    margin-bottom: 10px;
  }

  .subtitle {
    font-size: calc(100vw * (22 / 1920));
    font-family: 'Abril Fatface', cursive;
    font-weight: normal;
    font-style: normal;
    font-stretch: normal;
    line-height: 1.73;
    letter-spacing: normal;
    text-align: left;
    color: #91b260;
    margin-bottom: 30px;
  }

  .desc {
    font-size: calc(100vw * (26 / 1920));
    font-weight: normal;
    font-style: normal;
    font-stretch: normal;
    line-height: 1.73;
    letter-spacing: normal;
    text-align: left;
    color: #000000;
  }
}

.imglist {
  width: 100%;
  position: absolute;
  bottom: 0;
  display: flex;

  img {
    display: block;
    width: 25%;
    object-fit: cover;
  }
}

.right {
  width: 42.8vw;

  img {
    width: 100%;
    height: 100vh;
    // width: 100%;
  }
}

@media only screen and (max-width: 1280px) and (min-width: 1025px) {
  .fullscreen {
    // height: 100vh;
  }

  .right {
    img {
      height: auto;
    }
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

    > div {
      display: block;
    }

    &.fullscreen {
      height: auto !important;
    }
  }

  .m-content {
    background-image: url('./mobg.jpg');
    background-size: cover;
    padding-top: 50px;
    padding: 50px 18px 45px;

    .title {
      font-size: 39.5px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      line-height: 0.66;
      letter-spacing: normal;
      text-align: left;
      color: #507913;
      margin-bottom: 10px;
    }

    .subtitle {
      font-size: 15px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.73;
      letter-spacing: normal;
      text-align: left;
      color: #91b260;
      margin-bottom: 20px;
    }

    .desc {
      font-size: 16px;
      font-weight: normal;
      font-style: normal;
      font-stretch: normal;
      line-height: 1.59;
      letter-spacing: normal;
      text-align: left;
      color: #000000;
    }
  }

  .imgb {
    width: 100vw;
    display: block;
  }

  .img {
    width: 25%;
    display: block;
  }

  .imgmlist {
    display: flex;
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

  methods: {},
}
</script>
