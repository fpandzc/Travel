<template>
  <div class="header">
    <span class="header-left iconfont">&#xe658;</span>
    <div class="header-input">
      <span class="iconfont search-icon">&#xe63c;</span>
      输入城市/景点/游玩主题
    </div>
    <span class="header-right">
      城市
      <span class="iconfont down-icon">&#xe65c;</span>
    </span>
  </div>
</template>

<script>
    export default {
        name: "HomeHeader"
    }
</script>

<style lang="stylus" scoped>
  .header
    display: flex
    line-height: .86rem
    align-items: center
    background: #00bcd4
    font-size: .3rem
    color: #fff
    .header-left
      width: .8rem
      padding: 0 0 0 .2rem
      text-align: center
      font-size: .64rem
    .header-input
      width: 5.4rem
      line-height: .6rem
      border-radius: .06rem
      background: #fff
      color: #cccccc
      .search-icon
        padding: .04rem 0 0 .1rem
        font-size: .4rem
    .header-right
      width: 1.28rem
      padding: 0 0 0 .2rem
      .down-icon
        margin: -.1rem 0 0 -.2rem
        font-size: .44rem
</style>
