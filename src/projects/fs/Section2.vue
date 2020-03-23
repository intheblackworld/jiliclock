<template>
  <div class="section2">
    <div class="bg">
      <div v-if="!isMobile">
        <!-- <img src="./s1/bg1.png" alt class="bg-img relative" data-aos="fade" data-aos-delay="600" /> -->
        <img src="./s1/bg2.png" alt class="bg-img img-1" />
        <img src="./s1/bg3.jpg" alt class="bg-img img-2" />
      </div>
      <div v-else>
        <Map :tagList="tagList" :bgSrcT="bgSrcT" :bgSrcB="bgSrcB" :hand="hand" :bgText="require('./s2/text.png')">
          <img
            src="./s2/bg_icon.png"
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

#section2{
  position: relative;}
.bg {
  background-size: cover;
  background-position: center;
  position: relative;
  position: relative;
  // top: -24vw;
  // margin-bottom: -24vw;
}
.bg-img {
  width: 100vw;
  height: 100vh;
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
.img-2 {
  position: relative;
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
  .map-bg {
    z-index: 1;
  }
  .line {
    z-index: 2;
  }
  img.aos-init {
    z-index: 3;
  }
  .mask {
    z-index: 5;
    animation: swing 2.5s ease-in-out 0s infinite;
    background-image: url('./s2/bg_m.png');
  }

  .bg-img {
    width: auto;
    height: 100vh;
    &:nth-child(1) {
      position: absolute;
    }
  }
}
@keyframes swing {
  0% {
    transform: translateX(20px);
  }

  50% {
    transform: translateX(-20px);
  }

  100% {
    transform: translateX(20px);
  }
}
</style>
<script>
// @ is an alias to /src
import Map from '@/components/Map.vue'
import { isMobile } from '@/utils'
export default {
  name: 'section2',

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
      bgSrcT: require('./s2/bg_01.png'),
      bgSrcB: require('./s2/bg_02.jpg'),
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