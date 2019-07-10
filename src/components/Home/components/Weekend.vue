<template>
    <div class="weekend">
      <div class="tittle">周末去哪儿</div>
      <div class="contents">
        <div class="item" v-for="item of weekendList" :key="item.id">
          <img class="item-img" :src="item.imgUrl" alt="">
          <div class="item-info">
            <p class="item-name">{{item.name}}</p>
            <p class="item-desc">{{item.desc}}</p>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
    export default {
        name: "Weekend",
      data () {
          return {
            weekendList: [
              {
                id: '001',
                imgUrl: 'http://img1.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg',
                name: '清远周边逛',
                desc: '人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'
              },{
                id: '002',
                imgUrl: 'http://img1.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg',
                name: '清远周边逛',
                desc: '人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'
              },{
                id: '003',
                imgUrl: 'http://img1.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg',
                name: '清远周边逛',
                desc: '人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'
              },{
                id: '004',
                imgUrl: 'http://img1.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg',
                name: '清远周边逛',
                desc: '人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'
              },{
                id: '005',
                imgUrl: 'http://img1.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg',
                name: '清远周边逛',
                desc: '人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'
              },{
                id: '006',
                imgUrl: 'http://img1.qunarzz.com/sight/source/1811/15/66f14e0fd6fbb.jpg_r_640x214_5d69f21d.jpg',
                name: '清远周边逛',
                desc: '人人都有一双发现美的眼睛，身边的事物最熟悉不过，那你可曾发现了被人遗漏的美？'
              }
            ]
          }
      }
    }
</script>

<style lang="stylus" scoped>
  .weekend
    background #f5f5f5
    .tittle
      font-size .28rem
      padding .2rem 0 .2rem .26rem
      color #212121
    .contents
      width 100%
      .item
        margin-bottom .1rem
        .item-img
          width 100%
          height 36.65%
        .item-info
          background #ffffff
          padding .14rem .2rem .2rem .2rem
          .item-name
            font-size .28rem
            line-height .48rem
            padding-right 1.4rem
            color #212121
          .item-desc
            font-size .24rem
            line-height .42rem
            padding-right 1.4rem
            color #616161
            overflow hidden
            white-space nowrap
            -ms-text-overflow: ellipsis
            text-overflow: ellipsis
</style>
