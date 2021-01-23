<template>
  <div>
    <home-header></home-header>
    <swiper-map></swiper-map>
    <icons></icons>
  </div>
</template>

<script>

import HomeHeader from '@/components/HomeHeader'
import SwiperMap from '../components/Swiper'
import Icons from '../components/Icons'

export default {
  name: 'Home',
  components: {
    Icons,
    SwiperMap,
    HomeHeader
  }
}
</script>
