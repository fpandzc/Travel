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
      data () {
        return {
          swiperOption: {
            pagination: '.swiper-pagination'
          },
          iconList: [
            {
              id: '001',
              imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
              desc: '景点门票'
            },{
              id: '002',
              imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
              desc: '深圳游玩'
            },{
              id: '003',
              imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/4d/a1eda1a2b8414302.png',
              desc: '暑期夜场'
            },{
              id: '004',
              imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png',
              desc: '海洋馆'
            },{
              id: '005',
              imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/bda58ffc3016edad84e656e8a94b0321.png',
              desc: '广州融创'
            },{
              id: '006',
              imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
              desc: '深圳动物园'
            },{
              id: '007',
              imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/a6/6d97515091789602.png',
              desc: '世界之窗'
            },{
              id: '008',
              imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/b6/37560ece9c62b502.png',
              desc: '东部华侨城'
            },{
              id: '009',
              imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
              desc: '水上乐园'
            },{
              id: '010',
              imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/b1/528a9e80403b8c02.png',
              desc: '玩转长隆'
            }
          ]
        }
      },
      computed: {
        pages () {
          const pages = []

          this.iconList.forEach((item, index)=>{
            const page = Math.floor(index / 8)
            if (!pages[page]) {
              pages[page] = []
            }
            pages[page].push(item)
          })

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
