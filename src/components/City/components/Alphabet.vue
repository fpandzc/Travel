<template>
  <div>
    <ul class="alphabet">
      <li class="item" v-for="item of alphabet" :key="item">{{item}}</li>
    </ul>
  </div>
</template>

<script>
    export default {
      name: "Alphabet",
      props: {
        alphabet: Array
      }
    }
</script>

<style lang="stylus" scoped>
  @import "~@styles/varibles.styl"

  .alphabet
    display flex
    flex-direction column
    justify-content center
    position absolute
    top 1.86rem
    right 0
    bottom 0
    font-size .28rem
    color $bgcolor
    .item
      line-height .4rem
      text-align center
</style>
