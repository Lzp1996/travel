<template>
  <div>
    <router-link tag="div" v-show="showAbs" to="/" class="header-abs">
      <div class="iconfont icon-back">&#xe624;</div>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      景点详情
      <router-link tag="div" to="/">
        <div class="iconfont icon-fixed-back">&#xe624;</div>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.showAbs = false
        this.opacityStyle = { opacity }
      } else {
        this.showAbs = true
      }
    }
  },
  mounted () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  .header-abs
    position: absolute;
    top :.1rem
    left :.2rem
    width: .8rem
    height: .8rem
    line-height: .8rem;
    text-align :center
    background-color : rgba(0,0,0, .8)
    border-radius :.4rem
    .icon-back
      color :#ffffff
  .header-fixed
    position :fixed
    top :0
    width: 100%
    height: .86rem
    line-height: .86rem
    text-align: center
    color :#ffffff
    background-color :#25a4bb
    .icon-fixed-back
      position : absolute
      top :0
      left :0
      width: .64rem
      text-align :center
      font-size: .5rem;
</style>
