<template>
  <div class="container">
    <div class="item b-1px-b" v-for="(item,index) of  detailList" :key="index">
      {{item.tittle}}
      <span class="desc-price" v-if="item.price">
        <span class="price-logo">￥</span>
        <span class="price-number">{{item.price}}</span>
        <span class="price-text">起</span>
      </span>
      <div v-if="item.list" class="item-children">
        <detail-list  :detailList="item.list"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
    export default {
      name: "DetailList",
      props: {
        detailList: Array
      }
    }
</script>

<style lang="stylus" scoped>
  .container
    .item
      box-sizing border-box
      width 100%
      line-height .88rem
      padding 0 0 0 .2rem
      color #333333
      font-size .32rem
      .item-children
        .item
          width 100%
          font-size .28rem
          display flex
          justify-content space-between
          .desc-price
            font-size .24rem
            .price-logo
              color #ff8300
            .price-number
              margin-left -.08rem
              color #ff8300
              font-size .4rem
              font-weight bold
            .price-text
              color #616161
              margin-left -.08rem
              padding-right 0.4rem
</style>
