<template>
  <div>
    <city-header></city-header>
    <search></search>
    <city-list :city="city"></city-list>
    <alphabet :alphabet="alphabet"></alphabet>
  </div>
</template>

<script>
  import CityHeader from './components/CityHeader'
  import Search from './components/Search'
  import CityList from './components/CityList'
  import Alphabet from './components/Alphabet'

  export default {
    name: "City",
    components: {
      CityHeader,
      Search,
      CityList,
      Alphabet
    },
    data () {
      return {
        city: [],
        alphabet: []
      }
    },
    created () {
      this.axios.get('/api/city.json').then((res) => {
        const data = res.data

        this.city = data.city
        this.alphabet = data.alphabet
      })
    }
  }
</script>

<style scoped>

</style>
