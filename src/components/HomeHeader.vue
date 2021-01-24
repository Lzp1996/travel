<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont icon-back">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      <input type="text" placeholder="输入城市/景点/游玩主题" class="search">
    </div>
    <router-link to="/city">
      <div class="header-right">
        北京
        <span class="iconfont arrow-icon">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    hotCity: {
      type: Array
    }
  }
}
</script>

<style lang="stylus" scoped>
  .header
    display :flex
    height: 43px
    line-height: 43px
    background-color :#25a4bb
    text-align center
    .header-left
      float : left
      width: 43px
      .icon-back
        font-size: 20px
    .header-input
      display :flex;
      flex :1
      height : 32px
      line-height: 32px
      margin-top : 6px
      margin-left :5px
      background-color :#ffffff
      .search
        width: 100%
        height: 100%
        box-sizing :border-box
        padding :4px
    .header-right
      float : right
      width: 60px
      color :#ffffff
</style>
