<template>
    <div class="recommend">
      <div class="space"></div>
      <div class="tittle">热门推荐</div>
      <div class="contents">
        <div class="content-item b-1px-b"
             v-for="(item,index) of recommendList"
             :key="index">
          <img class="item-logo"
               :src="item.imgUrl"
               alt="Travel img">
          <div class="item-desc">
            <p class="desc-name">{{item.name}}</p>
            <div class="desc-price">
              <span class="price-logo">￥</span>
              <span class="price-number">{{item.price}}</span>
              <span class="price-text">起</span>
            </div>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
    export default {
        name: "HomeRecommend",
        data () {
          return {
            recommendList: [
              {
                imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/2e/d9363ce50a88c8c5ff5a138c67687cd4.water.jpg_200x200_1c15c8f5.jpg',
                name: '深圳野生动物园',
                price: '99'
              },{
                imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/2e/d9363ce50a88c8c5ff5a138c67687cd4.water.jpg_200x200_1c15c8f5.jpg',
                name: '深圳野生动物园',
                price: '99'
              },{
                imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/2e/d9363ce50a88c8c5ff5a138c67687cd4.water.jpg_200x200_1c15c8f5.jpg',
                name: '深圳野生动物园',
                price: '99'
              },{
                imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/2e/d9363ce50a88c8c5ff5a138c67687cd4.water.jpg_200x200_1c15c8f5.jpg',
                name: '深圳野生动物园',
                price: '99'
              },{
                imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/2e/d9363ce50a88c8c5ff5a138c67687cd4.water.jpg_200x200_1c15c8f5.jpg',
                name: '深圳野生动物园',
                price: '99'
              },{
                imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/2e/d9363ce50a88c8c5ff5a138c67687cd4.water.jpg_200x200_1c15c8f5.jpg',
                name: '深圳野生动物园',
                price: '99'
              },{
                imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/2e/d9363ce50a88c8c5ff5a138c67687cd4.water.jpg_200x200_1c15c8f5.jpg',
                name: '深圳野生动物园',
                price: '99'
              }
            ]
          }
        }
    }
</script>

<style lang="stylus" scoped>
  .recommend
    .space
      height .2rem
      background #cccccc
      opacity 0.4
    .tittle
      font-size .32rem
      padding .24rem 0
      margin-left .2rem
    .contents
      width 100%
      font-size .24px
      .content-item
        height 2.4rem
        display flex
        justify-content flex-start
        align-items center
        .item-logo
          width 2rem
          height 2rem
          margin-left .2rem
        .item-desc
          display flex
          flex-direction column
          justify-content center
          padding-left .2rem
          .desc-name
            font-size .32rem
            padding-bottom .6rem
            color #212121
          .desc-price
            .price-logo
              color #ff8300
            .price-number
              margin-left -.08rem
              color #ff8300
              font-size .4rem
              font-weight bold
            .price-text
              color #616161
</style>
