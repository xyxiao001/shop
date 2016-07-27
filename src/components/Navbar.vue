<template lang="html">
  <header>
    <section class="show-logo">
      <span v-on:click="menu"><i class="fa fa-bars"></i></span>
      <a v-link="{name: 'Dashboard', exact: true}" class="logo">积分商城</a>
      <span><i class="fa fa-cart-plus" aria-hidden="true"></i></span>
    </section>
    <section class="menu" v-bind:class="{ 'menu-hide': hideMenu, 'menu-show': showMenu }">
      <a v-link="{name: 'Dashboard', exact: true}">
        <i class="fa fa-home"></i>
        <span>首页</span>
      </a>
      <a href="#">
        <i class="fa fa-clone"></i>
        <span>热门</span>
      </a>
      <a href="#">
        <i class="fa fa-th"></i>
        <span>分类</span>
      </a>
      <a href="#">
        <i class="fa fa-user"></i>
        <span>个人</span>
      </a>
    </section>
  </header>
</template>

<script>
export default {
  data: function () {
    return {
      hideMenu: true,
      showMenu: false
    }
  },
  computed: {},
  ready: function () {},
  attached: function () {},
  methods: {
    menu () {
      if (this.hideMenu === true) {
        this.hideMenu = false
        this.showMenu = true
      } else {
        this.hideMenu = true
        this.showMenu = false
      }
    }
  },
  components: {}
}
</script>

<style lang="scss">
  a, a:hover, a:visited, a:focus{
    color: #666;
    text-decoration: none;
  }

  header {
    width: 100%;
    height: 50px;
    position: relative;
    font-size: 23px;
    // border-bottom: 1px solid rgba(88, 85, 25, 0.2);

    section.show-logo {
      padding: 8px 15px 10px 15px;

      i {
        float: left;
        padding-top: 8px;
        font-size: 23px;
        opacity: 0.8;
      }

      i.fa-cart-plus {
        float: right;
        padding-top: 12px;
        font-size: 23px;
        margin-top: -40px;
      }

      .logo {
        display: block;
        width: 150px;
        text-align: center;
        margin: auto;
        color: #ac2627;
        font-weight: bold;
      }
    }
    section.menu {
      position: absolute;
      z-index: 0;
      top: 99%;
      left: 0;
      width: 100%;
      transition: all 0.25s ease-out;
      font-size: 16px;
      overflow: hidden;
      color: #666;
      background-color: white;
      z-index: 999;

      a {
        display: inline-block;
        width: 23%;
        height: 95%;
        text-align: center;
        padding-top: 12px;
        color: #666;

        i {
          display: block;
          font-size: 25px;
        }

        span {
          display: block;
          font-size: 14px;
          margin-top: 1px;
          margin-left: 5px;
          letter-spacing: 2px;
        }
      }
    }

    section.menu-show {
      height: 65px;
      opacity: 1;
      border-top: 1px solid #d9d9d9;
    }

    section.menu-hide {
      height: 0px;
      opacity: 0;
    }
  }

</style>
