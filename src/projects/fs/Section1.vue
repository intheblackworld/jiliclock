<template>
  <div>
    <div class="bg">
      <div v-if="!isMobile">
        <img v-lazy="require('./s1/bg1.png')" alt class="bg-img" />
        <img
          :src="require('./s1/toplogo.png')"
          alt
          class="top-logo"
          data-aos="fade"
          data-aos-delay="300"
        />
        <img :src="require('./s1/logo.gif')" alt class="logo" data-aos="fade" data-aos-delay="300" />
        <img
          :src="require('./s1/text.png')"
          alt
          class="title-img"
          data-aos="fade"
          data-aos-delay="300"
        />
      </div>
      <div class="relative section" id="section2" v-if="!isMobile">
        <img v-lazy="require('./s1/bg2.png')" alt class="bg-img img-1" />
        <img v-lazy="require('./s1/bg3.jpg')" alt class="bg-img img-2" />
      </div>
      <div v-if="isMobile">
        <img :src="require('./s1/logo.gif')" alt class="logo" data-aos="fade" data-aos-delay="300" />
        <img :src="require('./mo/12/bg1.png')" alt class="bg-img" />
        <img :src="require('./mo/12/text.png')" alt class="bg-img" />
      </div>
      <div class="section" id="section2" v-if="isMobile">
        <Map
          :tagList="tagList"
          :bgSrcT="bgSrcT"
          :bgSrcB="bgSrcB"
          :hand="hand"
          :bgText="''"
        >
          <img
            src="./mo/12/bg_m.png"
            alt
            class="mask"
            v-if="isMobile"
            @click="hideMask"
            v-show="showMask"
          />
          <img
            src="./mo/12/bg_icon.png"
            alt
            class="mask"
            v-if="isMobile"
            @click="hideMask"
            v-show="showMask"
          />
        </Map>
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
  height: size(2100);
  background-image: linear-gradient(
    136deg,
    #064849,
    #064849 13%,
    #628963 20%,
    #87a6a2 27%,
    #628963 33%,
    #064849 40%,
    #064849 53%
  );
  z-index: 1;
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
    // mix-blend-mode: screen;
    // opacity: 0;
  }
}

.bg-all {
  width: 100vw;
  height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
  display: block;
  object-fit: cover;
}

.bg-2 {
  position: relative;
}

.img-2 {
  position: relative;
}

.logo {
  width: size(370);
  top: size(262);
  left: 0;
  right: 0;
  margin: 0 auto;
  position: absolute;
}

.top-logo {
  width: size(230);
  left: 0;
  top: 0;
  position: absolute;
}

.title-img {
  width: size(464);
  top: size(735);
  left: 0;
  right: 0;
  margin: 0 auto;
  position: absolute;
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
    height: size_m(1161);
  }
  .logo {
    width: size-m(185);
    top: size-m(240);
    left: 0;
    right: 0;
    margin: 0 auto;
    position: absolute;
    z-index: 1;
  }
  .bg-img {
    // &:nth-child(1) {
    //   position: absolute;
    //   z-index: 2;
    //   // mix-blend-mode: screen;
    //   // opacity: 0;
    // }
  }
  #section2 {
    position: absolute;
    top: size-m(581);
  }
}
</style>
<script>
// @ is an alias to /src
import Map from '@/components/Map.vue'
import { isMobile } from '@/utils'

export default {
  name: 'section1',
  components: {
    Map,
  },
  data() {
    return {
      isMobile,
      showMask: isMobile,
      mapText: [
        {
          title: '',
          desc: '',
        },
        {
          title: '',
          desc: '',
        },
      ],
      tagList: [],
      bgSrcT: require('./mo/12/bg2.png'),
      bgSrcB: require('./mo/12/bg3.jpg'),
      hand: '',
    }
  },

  methods: {
    hideMask() {
      this.showMask = false
    },
  },

  mounted() {},

  computed: {},
}
</script>
