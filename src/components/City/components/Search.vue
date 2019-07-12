<template>
  <div>
    <div class="search">
      <input class="search-input"
             type="text"
             placeholder="请输入城市名/拼音"
             v-model="keyword">
    </div>
    <div class="search-content" v-show="inSearch" ref="searchList">
      <ul>
        <li class="search-item b-1px-b"
            v-for="item of list"
            @click="handleChooseCity">{{item}}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
  import BScroll from 'better-scroll'
  import pinyin from 'pinyin'
  export default {
    name: "Search",
    props: {
      city: Array
    },
    data () {
      return {
        keyword: '',
        inSearch: false,
        timeout: null,
        list: []
      }
    },
    methods: {
      handleSearch (val) {
        const indexArr = pinyin(val,{
          style: pinyin.STYLE_NORMAL,
          heteronym: true,
          segment: true
        })

        let  index = ''
        console.info('indexArr:',indexArr)
        if (indexArr.length !== 0) {
          index =  indexArr[0].join('')
        }
        if(this.timer){
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          let list = [],
            city = []
          if(this.keyword === ''){
            this.inSearch = false
            return this.list= []
          }
          this.inSearch = true

          city = this.city.filter((item) => {
            return index.includes(item.initial.toLowerCase())
          })
          city.forEach((item) => {
            item.list.forEach((item)=>{
              // console.info(this.keyword,item.name,item.name.includes(this.keyword))
              if(item.name.includes(this.keyword) || item.pinyin.toUpperCase().includes(this.keyword.toUpperCase())){
                list.push(item.name)
              }
            })
          })
          return this.list = list
        },100)
      },
      handleChooseCity (e) {
        this.$store.commit('updateCity', e.target.innerText)
        this.$router.push('/')
      }
    },
    watch: {
      keyword () {
        this.handleSearch(this.keyword)
      }
    },
    mounted () {
      this.scroll = new BScroll(this.$refs.searchList,{
        preventDefault: false,
        probeType:1
      })
    }
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
  .search-content
    position absolute
    overflow hidden
    z-index 1
    top 1.86rem
    bottom 0
    left  0
    right 0
    background #fff
    font-size .28rem
    color #212121
    .search-item
      box-sizing border-box
      padding  0 0 0 .3rem
      height .9rem
      line-height .9rem
</style>
