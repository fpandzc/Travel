<template>
  <div class="city">
    <city-header></city-header>
    <search :city="city"></search>
    <city-list
      :city="city"
      :alphabet="alphabet"
      :currentIndex="currentIndex"
      @change="handleIndexChange"
    ></city-list>
    <alphabet
      :alphabet="alphabet"
      @change="handleAlphabetChange"
    >
    </alphabet>
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
        alphabet: [],
        currentIndex: 'A',
      }
    },
    methods: {
      handleAlphabetChange (Alphabet) {
        if(!(this.currentIndex ===  Alphabet)){
          this.currentIndex =  Alphabet
        }
      },
      handleIndexChange (index) {
        if(!(this.currentIndex ===  index)){
          this.currentIndex =  index
        }
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

<style lang="stylus" scoped>
  .city
    touch-action: manipulation
</style>
