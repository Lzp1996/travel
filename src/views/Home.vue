<template>
  <div>
    <home-header></home-header>
    <swiper-map></swiper-map>
  </div>
</template>

<script>

import HomeHeader from '@/components/HomeHeader'
import SwiperMap from '../components/Swiper'

export default {
  name: 'Home',
  components: {
    SwiperMap,
    HomeHeader
  }
}
</script>
