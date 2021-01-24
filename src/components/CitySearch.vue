<template>
  <div class="search">
    <input class="search-input" type="text" placeholder="请输入城市">
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
  .search
    overflow :hidden
    height: .72rem
    padding : 0 .1rem
    background-color : #25a4bb
    .search-input
      box-sizing : border-box
      width: 100%
      height: .62rem
      padding : 0 .1rem
      line-height: .62rem
      text-align :center
      background-color :#ffffff
      border-radius :.1rem
      color :#666
</style>
