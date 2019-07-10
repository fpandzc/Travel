<template>
    <swiper class="swiper" :options="swiperOption">
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icons">
          <div class="icon" v-for="item of page" :key="item.id">
            <img class="icon-img" :src="item.imgUrl" alt="Travel Icon">
            <p class="icon-desc">{{item.desc}}</p>
          </div>
        </div>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
</template>

<script>
    export default {
      name: "HomeIcon",
      props: {
        iconList: Array
      },
      data () {
        return {
          swiperOption: {
            pagination: '.swiper-pagination'
          }
        }
      },
      computed: {
        pages () {
          const pages = []
          if (this.iconList.length) {
            this.iconList.forEach((item, index) => {
              const page = Math.floor(index / 8)
              if (!pages[page]) {
                pages[page] = []
              }
              pages[page].push(item)
            })
          }
          return pages;
        }
      }
    }
</script>

<style lang="stylus" scoped>
  @import "~@styles/varibles.styl"
  .swiper >>> .swiper-pagination-bullets
    margin: 0 0 -.2rem 0
  .swiper >>> .swiper-pagination-bullet
    opacity: 0.5
  .swiper >>> .swiper-pagination-bullet-active
    background: $bgcolor
    opacity: 1
  .icons
    display: flex
    flex-flow: row wrap
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 3.7rem
    font-size: .28rem
    .icon
      display: flex
      width: 25%
      height: 1.5rem
      flex-flow: column wrap
      align-items: center
      padding: .1rem 0 0 0
      .icon-img
        width: 1.1rem
        height: 1.1rem
      .icon-desc
        padding: .1rem 0 0 0
</style>
