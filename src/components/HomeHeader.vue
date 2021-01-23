<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont icon-back">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      <input type="text" placeholder="输入城市/景点/游玩主题" class="search">
    </div>
    <div class="header-right">
      城市
      <span class="iconfont icon-arrow">&#xe64a;</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  .header
    display : flex
    height: 43px
    line-height: 43px
    text-align center
    background-color : #25a4bb
    color : #ffffff
    .header-left
      float : left
      width: 32px
      .icon-back
        font-size: 20px;
    .header-input
      display :flex
      flex : 1
      height: 32px
      line-height: 32px;
      margin-top : 6px
      margin-left : 10px
      text-align :left
      background-color :#ffffff
      color : black
      .search
        width: 100%
        height: 100%
        box-sizing :border-box
        outline : none
        padding : 4px
    .header-right
      float :right
      width: 60px
      .icon-arrow
        margin-left :-5px
</style>
