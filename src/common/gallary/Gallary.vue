<template>
  <div class="container" @click="handleGallaryClick">
    <div class="wrapper">
      <swiper :options="swiperOptions">
        <swiper-slide v-for="(item, index) of imgs" :key="index">
          <img class="swiper-img" :src="item"/>
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Gallary',
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  methods: {
    handleGallaryClick () {
      this.$emit('close')
    }
  },
  data () {
    return {
      swiperOptions: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  .container >>> .swiper-container
    overflow : inherit
  .container
    display : flex
    flex-direction : column
    justify-content : center
    position : fixed
    z-index : 99
    top : 0
    left : 0
    right : 0
    bottom : 0
    background-color : #000
    .wrapper
      width: 100%
      height: 0
      padding-bottom : 100%
      .swiper-img
        width: 100%
      .swiper-pagination
        color :#fff
        bottom : -1rem
</style>
