<template lang="html">
  <div class="content">
    <Navbar></Navbar>
    <Slide :items="slideImg"></Slide>
    <Notice :notices ="notices"></Notice>
    <div class="hot-commodity commodity">
      <div class="title">
        <a href="#">
          热门兑换  <i class="fa fa-angle-right" aria-hidden="true"></i>
        </a>
      </div>
      <div class="row">
        <Commodity v-for="hot in hots" :item="hot"></Commodity>
      </div>
    </div>
    <div class="less-time commodity">
      <div class="title">
        <a href="#">
          限时兑换  <i class="fa fa-angle-right" aria-hidden="true"></i>
        </a>
      </div>
      <div class="row">
        <Commodities v-for="lessTime in lessTimes" :item="lessTime"></Commodities>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from 'Navbar'
import Slide from 'SlideWarp'
import Notice from 'Notice'
import Commodity from 'Commodity'
import Commodities from 'Commodity-one'
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
      ],
      lessTimes: [
        {
          id: 201,
          src: 'http://yanxuan.nosdn.127.net/02d945e6598a1f777b504d29496ef015.png',
          name: '2条 皇室御用超柔面巾',
          des: '至柔至软',
          num: '50积分'
        },
        {
          id: 202,
          src: 'http://yanxuan.nosdn.127.net/8089dc57be56c0e30a93b048cb22c708.png',
          name: 'Ecolon不粘煎饼盘28cm',
          des: '放心源自天然矿物中提取的陶瓷涂层',
          num: '200积分'
        },
        {
          id: 203,
          src: 'http://yanxuan.nosdn.127.net/6925fe6e740fcaef92165528ccc3aa51.png',
          name: '6双 精梳棉提花隐形男袜',
          des: '撞色隐形袜，优雅随性',
          num: '100积分'
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
    Commodity,
    Commodities
  }
}
</script>

<style lang="scss">
  body {
    margin: auto;
    max-width: 768px;
  }

  .content {
    width: 100%;
    overflow: hidden;
  }

  .commodity {
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
