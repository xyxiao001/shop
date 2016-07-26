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
      showId: 0
    }
  },
  computed: {},
  props: ['items'],
  ready: function () {
    var that = this
    var slide = document.querySelector('.slideWarp')
    setInterval(function () {
      if (that.showId < 4) {
        that.showId = that.showId + 1
        slide.style.left = -(that.showId * 100) + '%'
        $('.show-control li').eq(that.showId).addClass('choose').siblings().removeClass('choose')
      } else {
        that.showId = 0
        slide.style.left = '0px'
        $('.show-control li').eq(0).addClass('choose').siblings().removeClass('choose')
      }
    }, 5000)
    $('.show-control li').click(function () {
      $(this).addClass('choose').siblings().removeClass('choose')
      that.showId = $(this).index()
      slide.style.left = -(that.showId * 100) + '%'
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
      transition: left 0.5s ease-out;

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
