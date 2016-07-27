<template lang="html">
  <div class="notice">
    <div class="laba">
      <i class="fa fa-bullhorn" aria-hidden="true"></i>
    </div>
    <div class="show-notice">
      <span v-for="notice in notices">{{ notice }}</span>
    </div>
  </div>
</template>

<script>
import $ from 'jquery'
export default {
  data: function () {
    return {
    }
  },
  props: ['notices'],
  computed: {},
  ready: function () {
    $('.show-notice').css('width', this.notices.length * 100 + '%')
  },
  attached: function () {},
  methods: {},
  components: {}
}
</script>

<style lang="scss">
  div.notice {
    position: relative;
    width: 100%;
    height: 35px;
    border-bottom: 1px solid rgba(88, 85, 25, 0.2);
    overflow: hidden;

    .laba {
      position: absolute;
      width: 35px;
      height: 30px;
      background-color: white;
      z-index: 98;

      i {
        color: #ac2627;
        font-size: 25px;
        padding: 5px;
      }
    }

    .show-notice {
      position: absolute;
      top: 8px;
      left: 40px;
      width: 100%;
      height: 25px;
      overflow: hidden;
      animation: showNotice 20s linear infinite;
      z-index: 1;

      span {
        display: inline-block;
        margin-left: 100px;
        word-break:keep-all;
        white-space:nowrap;
        color: #666;
      }

      .hide {
        display: none;
      }
    }
  }

  @keyframes showNotice {
    0% {
      left: 100%;
    }
    100% {
      left: -300%;
    }
  }
</style>
