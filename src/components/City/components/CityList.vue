<template>
  <div class="wrapper" ref="wrapper">
    <ul class="city-list">
      <li
        class="area"
        v-for="areaItem of city"
        :key="areaItem.initial"
        :ref="areaItem.initial"
      >
        <div class="area-header">{{areaItem.initial}}</div>
        <div class="area-contents" v-for="item of areaItem.list">
          <div class="item b-1px-b" @click="handleChooseCity">{{item.name}}</div>
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
        city: Array,
        currentIndex: String
      },
      data () {
        return {
          scrollStatus: false
        }
      },
      methods: {
        handleChooseCity (e) {
          this.$store.commit('updateCity', e.target.innerText)
          this.$router.push('/')
        }
      },
      mounted () {
        this.scroll = new BScroll(this.$refs.wrapper,{
          preventDefault: false,
          probeType:1
        })
      },
      watch: {
        currentIndex () {
          let el = this.$refs[this.currentIndex]
          if(el){
            el = this.$refs[this.currentIndex][0]
          }
          if(el){
            this.scroll.scrollToElement(el)
          }
        }
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
