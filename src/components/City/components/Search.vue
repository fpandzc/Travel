<template>
  <div class="search">
    <input class="search-input" type="text" placeholder="请输入城市名">
  </div>
</template>

<script>
    export default {
        name: "Search"
    }
</script>

<style lang="stylus" scoped>
  @import "~@styles/varibles.styl"

  .search
    display flex
    height .8rem
    padding .1rem
    background $bgcolor
    justify-content  center
    align-items center
    .search-input
      box-sizing border-box
      width 95%
      height .6rem
      padding 0 .2rem
      border-radius .1rem
      border none
      text-align center
      color #777777
</style>
