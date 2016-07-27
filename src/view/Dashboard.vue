<template lang="html">
  <Navbar></Navbar>
  <Slide :items="slideImg"></Slide>
  <Notice :notices ="notices"></Notice>
  <div class="hot-commodity">
    <div class="title">
      <a href="#">
        热门兑换  <i class="fa fa-angle-right" aria-hidden="true"></i>
      </a>
    </div>
    <div class="row">
      <Commodity v-for="hot in hots" :item="hot"></Commodity>
    </div>
  </div>
</template>

<script>
import Navbar from '../components/Navbar'
import Slide from '../components/SlideWarp'
import Notice from '../components/Notice'
import Commodity from '../components/Commodity'
export default {
  data: function () {
    return {
      slideImg: [
        {
          id: 1,
          src: 'http://yanxuan.nosdn.127.net/1aa6bc8e2079dccfa47a10ff06028fda.jpg?imageView&quality=85&thumbnail=750x400'
        },
        {
          id: 2,
          src: 'http://yanxuan.nosdn.127.net/42e2883b47df24b039922e87f75ea30a.jpg?imageView&quality=85&thumbnail=750x400'
        },
        {
          id: 3,
          src: 'http://yanxuan.nosdn.127.net/a06041c77d04d9025dce5ce144672602.jpg?imageView&quality=85&thumbnail=750x400'
        },
        {
          id: 4,
          src: 'http://yanxuan.nosdn.127.net/65f04feaddfc6f179f793e6dffc95f57.jpg?imageView&quality=85&thumbnail=750x400'
        },
        {
          id: 5,
          src: 'http://yanxuan.nosdn.127.net/51bfd8a82909b3a6225ccf7cb2b1325a.jpg?imageView&quality=85&thumbnail=750x400'
        }
      ],
      notices: [
        '恭喜用户001成功兑换iphone6s',
        '恭喜用户002成功兑换ipad Air2',
        '恭喜用户003成功兑换ipad Air2',
        '恭喜用户004成功兑换小米5'
      ],
      hots: [
        {
          id: 100,
          src: 'http://yanxuan.nosdn.127.net/07e2057d35153f063cf042177d6a815e.png?imageView&quality=85&thumbnail=330x330',
          name: '茶香酥200克',
          num: '300积分'
        },
        {
          id: 102,
          src: 'http://yanxuan.nosdn.127.net/d34867f2e905f76eb7c8f46dcb2e052f.png?imageView&quality=85&thumbnail=330x330',
          name: '带盖棉麻涤内衣收纳盒',
          num: '500积分'
        },
        {
          id: 103,
          src: 'http://yanxuan.nosdn.127.net/4fb112a597732ea093df1d495587b04e.png?imageView&quality=85&thumbnail=330x330',
          name: '速干防滑沐浴拖鞋',
          num: '250积分'
        },
        {
          id: 104,
          src: 'http://yanxuan.nosdn.127.net/f99b3e5bbd6fbf86bad98cfe3ad9c2d9.png?imageView&quality=85&thumbnail=330x330',
          name: 'Classic欧式压铸炒锅30cm',
          num: '3400积分'
        }
      ]
    }
  },
  computed: {},
  ready: function () {},
  attached: function () {},
  methods: {},
  components: {
    Navbar,
    Slide,
    Notice,
    Commodity
  }
}
</script>

<style lang="scss">
  body {
    margin: auto;
    max-width: 768px;
    overflow-x: hidden;
    overflow-y: scroll;
  }

  .hot-commodity {
    width: 100%;

    .title {
      height: 60px;
      text-align: center;
      font-size: 20px;
      padding-top: 15px;
      line-height: 1.5;
      color: #333;
    }
  }
</style>
