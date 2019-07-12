<template>
  <div>
    <ul class="alphabet">
      <li class="item"
          v-for="item of alphabet"
          :key="item"
          :ref="item"
          @touchstart="handleTouchStart"
          @touchmove="handleTouchMove"
          @touchend="handleTouchEnd"
          @click="handleClick">{{item}}
      </li>
    </ul>
  </div>
</template>

<script>
    export default {
      name: "Alphabet",
      props: {
        alphabet: Array
      },
      data () {
        return {
          touchStatus: false,
          timer: null
        }
      },
      methods: {
        handleClick (e) {
          this.$emit('change', e.target.innerText)
        },
        handleTouchStart () {
          this.touchStatus = true
        },
        handleTouchMove (e) {
          if(this.timer){
            clearTimeout(this.timer)
          }
          this.timer = setTimeout(() => {
            if (this.touchStatus) {
              const startY = this.$refs['A'][0].offsetTop,
                touchY = e.touches[0].clientY - 93,
                index = Math.floor((touchY - startY) / 20)
              this.$emit('change', this.alphabet[index])
            }
          },10)
        },
        handleTouchEnd () {
          this.touchStatus = false
        }
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
