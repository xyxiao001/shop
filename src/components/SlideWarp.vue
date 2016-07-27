<template lang="html">
  <section class="slide">
    <div class="slideWarp">
      <a class="slide-item" v-for="item in items">
        <img v-bind:src="item.src" v-bind:alt="item.id" />
      </a>
    </div>
    <div class="item-control">
      <ul class="show-control">
        <li class="choose"></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
      </ul>
    </div>
  </section>
</template>

<script>
import $ from 'jquery'

export default {
  data: function () {
    return {
    }
  },
  computed: {},
  props: ['items'],
  ready: function () {
    var showId = 0
    var slide = document.querySelector('.slideWarp')
    var setSlide = setInterval(function () {
      if (showId < 4) {
        showId = showId + 1
        var goLeft = -(showId * 100) + '%'
        $(slide).animate({left: goLeft})
        $('.show-control li').eq(showId).addClass('choose').siblings().removeClass('choose')
      } else {
        showId = 0
        $(slide).animate({left: '0px'})
        $('.show-control li').eq(0).addClass('choose').siblings().removeClass('choose')
      }
    }, 5000)
    $('.show-control li').click(function () {
      $(this).addClass('choose').siblings().removeClass('choose')
      showId = $(this).index()
      var goLeft = -(showId * 100) + '%'
      $(slide).animate({left: goLeft})
    })
    $(function () {
      var startX, endX, go, old
      // 屏幕大小
      var page = document.body.clientWidth
      var el = document.querySelectorAll('.slide-item')
      for (var i = 0; i < el.length; i++) {
        el[i].addEventListener('touchstart', touchStart, false)
        el[i].addEventListener('touchmove', touchMove, false)
        el[i].addEventListener('touchend', touchEnd, false)
      }
      function touchStart (event) {
        // 当用户按压屏幕 清除自动轮播
        clearInterval(setSlide)
        // 横坐标
        startX = event.touches[0].clientX
        // 本来有的
        old = slide.style.left || '00'
        old = old.substring(0, old.length - 1)
      }
      function touchMove (event) {
        endX = event.touches[0].clientX
        // 需要移动百分比
        go = (endX - startX) / page * 100
        var goes = Number(go) + Number(old)
        slide.style.left = (goes) + '%'
      }

      function touchEnd (event) {
        if (go < 0) {
          go = ~(go)
          // 需要前进次数
          var goId = Math.round(go / 100)
          showId = showId + goId
          if (showId > 4) {
            showId = 4
          }
        } else {
          if (showId !== 0) {
            // 需要后退次数
            goId = Math.round(go / 100)
            showId = showId - goId
          }
        }
        var goLeft = -(showId * 100) + '%'
        $(slide).animate({left: goLeft})
        $('.show-control li').eq(showId).addClass('choose').siblings().removeClass('choose')
      }
    })
  },
  attached: function () {},
  methods: {},
  components: {}
}
</script>

<style lang="scss">
  section.slide {
    position: relative;
    width: 100%;
    height: 200px;
    overflow: hidden;

    div.slideWarp {
      position: absolute;
      padding: 0;
      margin: 0;
      left: 0;
      width: 500%;
      height: 200px;
      overflow: hidden;
      z-index: 98%;
      //transition: left 0.5s ease-out;

      .slide-item {
        position: relative;;
        display: inline-block;
        width: 20%;
        cursor: pointer;

        img {
          width: 100%;
          height: 100%;
        }
      }
    }

    div.item-control {
      position: absolute;
      width: 150px;
      height: 50px;
      left: 50%;
      margin-left: -80px;
      top: 100%;
      margin-top: -25px;

      ul {
        margin: 0;
        width: 100%;
        height: 50px;
        padding-left: 0px;

        li {
          float: left;
          list-style-type: none;
          width: 15px;
          height: 15px;
          border-radius: 15px;
          margin-left: 15px;
          border: 1px solid #666;
          cursor: pointer;

          &.choose {
            background-color: #666;
          }
        }
      }
    }
  }

  @media screen and (max-width: 350px) {
    section.slide {

      div.item-control {
        margin-top: -50px;
      }
    }
  }

  @media  screen and (min-width: 800px) {
    section.slide {
      height: 400px;

      div.slideWarp {
        height: 400px;
      }
    }
  }
</style>
