<template lang="html">
  <div class="col-xs-12">
    <a href="#" class="one">
      <div class="row">
        <div class="col-xs-5">
          <div class="one-left">
            <img v-bind:src="item.src" v-bind:alt="item.id" />
          </div>
        </div>
        <div class="col-xs-7">
          <div class="one-right">
            <p class="name">{{ item.name }}</p>
            <p class="des">{{ item.des }}</p>
            <p class="num">{{ item.num }}</p>
            <span class="time">还剩3天</span>
          </div>
        </div>
      </div>
    </a>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
    }
  },
  computed: {},
  props: ['item'],
  ready: function () {},
  attached: function () {},
  methods: {},
  components: {}
}
</script>

<style lang="scss">
  a.one {
    display: block;
    width: 100%;
    height: 125px;
    overflow: hidden;
  }

  .one-left {
    width: 90%;
    height: 100%;
    margin: auto;

    img {
      width: 100%;
      height: 100%;
    }
  }

  div.one-right {
    padding-top: 35px;
    height: 100%;

    p {
      font-size: 15px;
      margin: 3px;
      letter-spacing: 1px;
      text-overflow: ellipsis;
      white-space: nowrap;
      overflow: hidden;
    }

    p.name {
      color: #333;
    }

    p.des {
      font-size: 14px;
      color: #999;
    }

    p.num {
      color: #ab2b2b;
    }

    span.time {
      float: right;
      font-size: 14px;
      margin-top: -20px;
      margin-right: 10px;
      color: #666;
    }
  }

  @media screen and (min-width: 600px) {
    a.one {
      height: 250px;
    }

    div.one-right {
      padding-top: 100px;
      padding-left: 30px;
      height: 100%;
    }
  }

  @media screen and (max-width: 340px) {
    div.one-right {
      padding-top: 10px;
    }
  }
</style>
