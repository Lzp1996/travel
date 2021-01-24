<template>
  <div>
    <home-header ></home-header>
    <swiper-map :list="swiperList"></swiper-map>
    <icons :list="iconList"></icons>
    <recommend :list="recommendList"></recommend>
  </div>
</template>

<script>

import HomeHeader from '@/components/HomeHeader'
import SwiperMap from '../components/Swiper'
import Icons from '../components/Icons'
import Recommend from '../components/Recommend'
import axios from 'axios'
export default {
  name: 'Home',
  data () {
    return {
      swiperList: [],
      iconList: [],
      recommendList: []
    }
  },
  components: {
    Recommend,
    Icons,
    SwiperMap,
    HomeHeader
  },
  methods: {
    getHomeInfo () {
      axios.get('/static/index.json')
        .then(res => {
          res = res.data
          if (res.ret && res.data) {
            const data = res.data
            this.swiperList = data.swiperList
            this.iconList = data.iconList
            this.recommendList = data.recommendList
          }
        })
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>
