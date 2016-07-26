<template lang="html">
  <header>
    <section class="show-logo">
      <span><i class="fa fa-bars"></i></span>
      <a class="logo">积分商城</a>
      <span><i class="fa fa-cart-plus" aria-hidden="true"></i></span>
    </div>
  </section>
</template>

<script>
export default {
  data: function () {
    return {
    }
  },
  computed: {},
  ready: function () {},
  attached: function () {},
  methods: {},
  components: {}
}
</script>

<style lang="scss">
  a, a:hover, a:visited, a:focus{
    color: black;
    text-decoration: none;
  }

  header {
    width: 100%;
    height: 50px;
    font-size: 23px;
    border-bottom: 1px solid gray;

    section.show-logo {
      padding: 8px 15px 10px 15px;

      i {
        float: left;
        padding-top: 8px;
        font-size: 23px;
      }

      i.fa-cart-plus {
        float: right;
        padding-top: 12px;
        font-size: 23px;
        margin-top: -40px;
      }

      .logo {
        display: block;
        width: 200px;
        text-align: center;
        margin: auto;
      }
    }
  }

</style>
