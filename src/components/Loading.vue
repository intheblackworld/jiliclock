<template>
  <div :class="`loading-bg ${loading ? '' : 'hide'} ${isOpacity ? 'opacity': ''}`">
    <!-- <img src="~@/assets/img/loading_b.gif" alt class="loading-icon" /> -->
     <rotate-square2></rotate-square2>
  </div>
</template>

<style lang="scss" scoped>
@import '@/assets/style/variableColor.scss';

.loading-bg {
  background-color: $loading_bg_color;
  background-image: $loading_bg_image;
  position: fixed;
  left: 0;
  top: 0;
  z-index: 1000;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100vw;
  height: 100vh;

  .loading-icon {
    width: 150px;
    border-color: $loading_icon_color;
  }

  &.opacity {
    opacity: .8;
  }

  &.hide {
    animation: hide .3s ease 0s forwards;
  }

  &.none {
    display: none;
  }

  @keyframes hide {
    0% {
      oacity: 1;
      display: block;
    }

    99% {
      opacity: 0;
      display: block;
      z-index: 1000;
    }

    100% {
      opacity: 0;
      display: none;
      z-index: -1000;
    }
  }
}
</style>

<script>
// import { setTimeout } from 'timers'
import { RotateSquare2 } from 'vue-loading-spinner'

export default {
  name: 'loadingComponent',

  props: ['loading', 'isOpacity'],

  components: {
    RotateSquare2
  },

  data() {
    return {
      remove: false,
    }
  },

  watch: {
    loading: {
      handler(loading) {
        this.remove = !loading
      },
      // immediate: true,
    },
  },

  // created() {
  //   setTimeout(() => {
  //     this.remove = true
  //   }, 1000)
  // },
}
</script>
