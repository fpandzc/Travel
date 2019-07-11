<template>
    <div class="header">
      <router-link to="/" tag="span" class="iconfont back-icon">&#xe658;</router-link>
      <span class="tittle">城市选择</span>
    </div>
</template>

<script>
    export default {
        name: "CityHeader"
    }
</script>

<style lang="stylus" scoped>
  @import "~@styles/varibles.styl"

  .header
    display flex
    line-height .86rem
    align-items center
    background $bgcolor
    font-size .3rem
    color #fff
    .back-icon
      padding 0 0 0 .16rem
      font-size .64rem
    .tittle
      width 5.5rem
      font-size .32rem
      text-align center
</style>
