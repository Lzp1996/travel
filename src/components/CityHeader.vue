<template>
  <div class="cityHeader">
    城市选择
    <router-link to="/">
      <div class="iconfont icon-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  .cityHeader
    position : relative
    overflow :hidden
    height: .86rem
    line-height: .86rem
    background-color :#25a4bb
    color :#ffffff
    text-align : center
    font-size: .4rem;
    .icon-back
      position :absolute
      top : 0
      left : 0
      font-size: .4rem;
      color :#ffffff
</style>
