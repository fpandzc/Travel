<template>
    <div>
      <home-header></home-header>
      <home-swiper></home-swiper>
      <home-icon></home-icon>
      <home-recommend></home-recommend>
      <weekend></weekend>
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
      methods: {
        getHomeInfo () {
          this.axios.get('/api/index').then((res)=>{
            console.info(res)
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
