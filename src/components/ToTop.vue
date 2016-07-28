<template lang="html">
 <i class="go-top"></i>
</template>

<script>
import $ from 'jquery'
export default {
  data: function () {
    return {
    }
  },
  computed: {},
  ready: function () {
    $(document).scroll(function () {
      if (window.scrollY > 500) {
        $('.go-top').show()
      } else {
        $('.go-top').hide()
      }
    })

    $('.go-top').click(function () {
      $('body').animate({ scrollTop: '0px' }, 500)
    })
  },
  attached: function () {},
  methods: {},
  components: {}
}
</script>

<style lang="scss">
  i.go-top {
    position: fixed;
    display: none;
    bottom: 10px;
    right: 15px;
    width: 50px;
    height: 50px;
    z-index: 100;
    background-image: url('../assets/top.png');
    background-size: cover;
  }
</style>
