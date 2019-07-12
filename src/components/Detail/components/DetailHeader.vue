<template>
  <div class="header">
    <router-link
      v-show="isDeafult"
      tag="div"
      to="/"
      class="default-header">
      <span class="iconfont back-icon">&#xe658;
      </span>
    </router-link>
    <div class="active-header" v-show="!isDeafult" :style="opacityStyle">
      <router-link
        to="/"
        class="iconfont back-icon"
        tag="div">&#xe658;
      </router-link>
      <span class="header-tittle">景点详情</span>
    </div>
  </div>
</template>

<script>
    export default {
      name: "DetailHeader",
      data () {
        return {
          isDeafult: true,
          opacityStyle: {
            opacity: 0
          }
        }
      },
      methods: {
        handleScroll() {
          const top = document.documentElement.scrollTop
          if (top < 45){
            this.isDeafult = true
          } else {
            let opacity = top / 120
            opacity = opacity > 1 ? 1:opacity
            this.opacityStyle = { opacity }
            this.isDeafult = false
          }
        }
      },
      mounted () {
        window.addEventListener('scroll',this.handleScroll)
      },
      beforeDestroy () {
        window.removeEventListener('scroll',this.handleScroll)
      }
    }
</script>

<style lang="stylus" scoped>
  @import "~@styles/varibles.styl"

  .header
    position absolute
    width 100%
    height .86rem
    top 0
    color #fff
    .default-header
      display flex
      align-items center
      justify-content center
      width .72rem
      height .72rem
      background rgba(0,0,0,.2)
      border-radius 50%
      margin  .1rem
      .back-icon
        font-size .68rem
    .active-header
      position fixed
      z-index 2
      display flex
      align-items center
      width 100%
      height .86rem
      font-size .32rem
      background $bgcolor
      .header-tittle
        flex 1
        line-height .86rem
        text-align center
      .back-icon
        position absolute
        margin  .1rem
        top 0
        font-size .68rem
</style>
