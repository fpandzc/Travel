<template>
  <div class="wrapper" ref="wrapper">
    <ul class="city-list">
      <li class="area" v-for="areaItem of city" :key="areaItem.initial">
        <div class="area-header">{{areaItem.initial}}</div>
        <div class="area-contents" v-for="item of areaItem.list" :key="item.code">
          <div class="item b-1px-b">{{item.name}}</div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
  import BScroll from 'better-scroll'

    export default {
      name: "CityList",
      props: {
        city: Array
      },
      mounted () {
        this.scroll = new BScroll(this.$refs.wrapper)
      }
    }
</script>

<style lang="stylus" scoped>
  .wrapper
    position absolute
    overflow hidden
    top 1.86rem
    bottom 0
    width 100%
    .city-list
      font-size .28rem
      color #212121
      .area
        .area-header
          padding  0 0 0 .3rem
          background #f5f5f5
          height .72rem
          line-height .72rem
        .area-contents
          .item
            box-sizing border-box
            padding  0 0 0 .3rem
            height .9rem
            line-height .9rem
</style>
