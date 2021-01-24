<template>
  <div>
    <city-header></city-header>
    <city-search :cityList="cities"></city-search>
    <city-list :hotCity="hotCity" :cities="cities" :letter="letter"></city-list>
    <alphabet :cities="cities" @change="getLetter"></alphabet>
  </div>
</template>

<script>
import CityHeader from '../components/CityHeader'
import CitySearch from '../components/CitySearch'
import CityList from '../components/CityList'
import axios from '_axios@0.21.1@axios'
import Alphabet from '@/components/Alphabet'
export default {
  name: 'City',
  data () {
    return {
      letter: '',
      cities: {},
      hotCity: []
    }
  },
  components: {
    Alphabet,
    CityList,
    CityHeader,
    CitySearch
  },
  methods: {
    getCityInfo () {
      axios.get('/static/city.json')
        .then(res => {
          res = res.data
          if (res.ret && res.data) {
            const data = res.data
            this.hotCity = data.hotCities
            this.cities = data.cities
          }
        })
    },
    getLetter (letter) {
      this.letter = letter
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style scoped>

</style>
