<template lang="html">
  <div class="col-xs-6">
    <a href="#" class="good-commodity">
      <img v-bind:src="item.src" v-bind:alt="item.id" />
      <p class="commodity-name">{{ item.name }}</p>
      <p class="commodity-num">{{ item.num }}</p>
    </a>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
    }
  },
  props: ['item'],
  computed: {},
  ready: function () {},
  attached: function () {},
  methods: {},
  components: {}
}
</script>

<style lang="scss">
  a.good-commodity {
    display: inline-block;
    width: 100%;
    height: 180px;

    img {
      width: 100%;
    }

    p {
      margin: 0;
      margin-top: -20px;
      text-align: center;
      font-size: 14px;
    }

    p.commodity-name {
      width: 90%;
      margin: auto;
      letter-spacing: 1px;
      text-overflow: ellipsis;
      white-space: nowrap;
      overflow: hidden;
    }

    p.commodity-num {
      margin-top: 5px;
      color: #ab2b2b;
    }
  }
</style>
