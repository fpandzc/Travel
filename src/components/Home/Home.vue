<template>
    <div>
      <home-header></home-header>
      <home-swiper></home-swiper>
      <home-icon></home-icon>
      <home-recommend></home-recommend>
    </div>
</template>

<script>
    import HomeHeader from './components/HomeHeader'
    import HomeSwiper from './components/HomeSwiper'
    import HomeIcon from './components/HomeIcon'
    import HomeRecommend from './components/HomeRecommend'
    export default {
      name: 'Home',
      components: {
        HomeHeader,
        HomeSwiper,
        HomeIcon,
        HomeRecommend
      }
    }
</script>

<style scoped>
</style>
