<template>
  <div class="container">
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerInfo.imgUrl" alt="">
    </div>
    <div class="info">
      <span class="info-name">{{bannerInfo.name}}</span>
      <span class="info-img">
        <span class="iconfont">&#xe634;</span>
        <span>{{bannerInfo.imgNum}}</span>
      </span>
    </div>
    <detail-swiper v-show="showSwiper" @close="handleClose" :swiperList="bannerInfo.swiperList"></detail-swiper>
  </div>
</template>

<script>
  import DetailSwiper from './DetailSwiper'

  export default {
    name: "Banner",
    components: {
      DetailSwiper
    },
    props: {
      bannerInfo: Object
    },
    data (){
      return {
        showSwiper: false
      }
    },
    methods: {
      handleBannerClick () {
        this.showSwiper = true
      },
      handleClose () {
        this.showSwiper = false
      }
    }
  }
</script>

<style lang="stylus" scoped>
  .container
    position relative
    .banner
      overflow hidden
      height 0
      width 100%
      padding-bottom 55%
      .banner-img
        width 100%
    .info
      display flex
      justify-content  space-between
      position absolute
      z-index 1
      width 100%
      min-height .4rem
      bottom .36rem
      color #fff
      .info-name
        padding 0 0 0 .2rem
        font-size .36rem
      .info-img
        padding 0 .2rem 0 0
        font-size .28rem
</style>
