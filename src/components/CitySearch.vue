<template>
  <div class="search">
    <input v-model="keyword" class="search-input" type="text" placeholder="请输入城市">
    <div class="search-content" v-show="keyword" ref="search">
      <ul>
        <li class="item" v-for="item of list" :key="item.id">{{item.name}}</li>
        <li class="item" v-show="hasCity">未搜索到指定城市</li>
      </ul>
    </div>
  </div>
</template>

<script>
import BScorll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cityList: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasCity () {
      return !this.list.length
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (const key in this.cityList) {
          this.cityList[key].forEach(city => {
            if (city.spell.indexOf(this.keyword) > -1 || city.name.indexOf(this.keyword) > -1) {
              result.push(city)
            }
          })
        }
        this.list = result
      }, 16)
    }
  },
  mounted () {
    this.scroll = new BScorll(this.$refs.search)
  }
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
    .search-content
      position : absolute
      overflow :hidden
      z-index : 1
      top : 1.55rem
      left : 0
      right : 0
      bottom : 0
      background-color : #e5e5e5
      .item
        line-height: .54rem;
        padding-left :.2rem
        border-bottom : .01rem solid #eaeaea
</style>
