<template>
  <div>
    <banner :bannerInfo="bannerInfo"></banner>
    <detail-header></detail-header>
    <detail-list :detailList="detailList"></detail-list>
    <div style="height: 2rem"></div>
  </div>
</template>

<script>
  import Banner from './components/Banner'
  import DetailHeader from './components/DetailHeader'
  import DetailList from './components/DetailList'

  export default {
    name: "Detail",
    components: {
      Banner,
      DetailHeader,
      DetailList
    },
    data () {
      return {
        bannerInfo: {},
        detailList: []
      }
    },
    methods: {
      getDetailInfo () {
        this.axios.get('/api/detailInfo.json').then((res)=>{
          const data = res.data

          this.bannerInfo = data.bannerInfo
          this.detailList = data.detailList
        })
      }
    },
    created () {
      this.getDetailInfo()
    }
  }
</script>

<style scoped>

</style>
