<template>
  <div class="container" @click="handleSwiperClick">
    <swiper class="swiper" :options="swiperOption">
        <swiper-slide v-for="item of swiperList" :key="item.id">
          <img class="swiper-img" :src="item.imgUrl" alt="Travel img">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
</template>

<script>
  export default {
    name: "DetailSwiper",
    props: {
      swiperList: Array
    },
    data () {
      return {
        swiperOption: {
          pagination: '.swiper-pagination',
          loop: true,
          paginationType: 'fraction',
          observeParents: true,
          observer: true
        }
      }
    },
    methods: {
      handleSwiperClick () {
        this.$emit('close')
      }
    }
  }
</script>

<style lang="stylus" scoped>
  .container
    touch-action manipulation
    position fixed
    display flex
    align-items  center
    z-index 99
    width 100%
    left 0
    right 0
    top 0
    bottom 0
    background #212121
    .swiper
      width 100%
      height 0
      overflow hidden
      padding-bottom 100%
      .swiper-img
        width 100%
      .swiper-pagination
        color #fff
        font-size .32rem
</style>
