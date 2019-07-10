<template>
  <swiper class="swiper" :options="swiperOption">
    <swiper-slide v-for="item of swiperList" :key="item.id">
      <img class="swiper-img" :src="item.imgUrl" alt="Travel img">
    </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</template>

<script>
    export default {
      name: "HomeSwiper",
      props: {
        swiperList: Array
      },
      data () {
        return {
          swiperOption: {
            pagination: '.swiper-pagination'
          }
        }
      }
    }
</script>

<style lang="stylus" scoped>
  .swiper >>> .swiper-pagination-bullet
    opacity: 0.5
  .swiper >>> .swiper-pagination-bullet-active
    background: #fff
    opacity: 1
  .swiper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 28%
    .swiper-img
      width: 100%
</style>
