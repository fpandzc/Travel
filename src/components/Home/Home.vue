<template>
    <div>
      <home-header :city="city"></home-header>
      <home-swiper :swiperList="swiperList"></home-swiper>
      <home-icon :iconList="iconList"></home-icon>
      <home-recommend :recommendList="recommendList"></home-recommend>
      <weekend :weekendList="weekendList"></weekend>
    </div>
</template>

<script>
    import HomeHeader from './components/HomeHeader'
    import HomeSwiper from './components/HomeSwiper'
    import HomeIcon from './components/HomeIcon'
    import HomeRecommend from './components/HomeRecommend'
    import Weekend from './components/Weekend'
    export default {
      name: 'Home',
      components: {
        HomeHeader,
        HomeSwiper,
        HomeIcon,
        HomeRecommend,
        Weekend
      },
      data () {
        return {
          city: '',
          swiperList: [],
          iconList: [],
          recommendList: [],
          weekendList: []
        }
      },
      methods: {
        getHomeInfo () {
          this.axios.get('/api/indexInfo.json').then((res)=>{
            const data = res.data

            this.city = data.city
            this.swiperList = data.swiperList
            this.iconList = data.iconList
            this.recommendList = data.recommendList
            this.weekendList = data.weekendList
          })
        }
      },
      created () {
        this.getHomeInfo()
      }
    }
</script>

<style scoped>
</style>
