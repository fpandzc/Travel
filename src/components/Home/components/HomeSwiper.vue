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
      data () {
        return {
          swiperOption: {
            pagination: '.swiper-pagination'
          },
          swiperList: [
            {
              id: '001',
              imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20197/5e7f9ad26e6b8a776781a4080fb913a3.jpg_750x200_83797280.jpg'
            }, {
              id: '002',
              imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/b23a39921e8b78f38b61412d691d93ea.jpg_750x200_942ed7bd.jpg'
            }
          ]
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
