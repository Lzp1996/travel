<template>
  <div>
    <div class="banner" @click="handleClickGallary">
      <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_600x330_bf9c4904.jpg" alt="">
      <div class="banner-info">
        <div class="banner-title">大连圣亚海洋世界(AAAA景区)</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe692;</span>
          39
        </div>
      </div>
    </div>
    <fade>
      <gallary :imgs="imgs" v-show="showGallary"  @close="handleCloseGallary"></gallary>
    </fade>
  </div>
</template>

<script>
import Gallary from '@/common/gallary/Gallary'
import Fade from '@/common/fade/Fade'
export default {
  name: 'Banner',
  data () {
    return {
      showGallary: false,
      imgs: [
        'http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_800x800_70debc93.jpg',
        'http://img1.qunarzz.com/sight/p0/1709/76/7691528bc7d7ad3ca3.img.png_800x800_9ef05ee7.png']
    }
  },
  methods: {
    handleClickGallary () {
      this.showGallary = true
    },
    handleCloseGallary () {
      this.showGallary = false
    }
  },
  components: { Fade, Gallary }
}
</script>

<style lang="stylus" scoped>
  .banner
    position : relative
    overflow : hidden
    width: 100%
    height : 0
    padding-bottom : 55%
    .banner-img
      width :100%
    .banner-info
      display :flex
      position :absolute
      left : 0
      right : 0
      bottom : 0
      line-height: .6rem;
      color : #ffffff
      background : linear-gradient(top, rgba(0,0,0,0) rgba(0,0,0,.8))
      .banner-title
        flex :1
        font-size: .32rem;
        padding : 0 .2rem
      .banner-number
        height: .32rem
        line-height: .32rem
        margin-top :.2rem
        padding : 0 .4rem
        background : rgba(0, 0, 0, .5)
        border-radius : .2rem
        font-size: .24rem;
        .banner-icon
          font-size: .24rem;
</style>
