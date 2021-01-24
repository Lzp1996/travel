<template>
  <div >
    <banner></banner>
    <detail-header></detail-header>
    <div class="h"></div>
  </div>
</template>

<script>
import Banner from '@/components/Banner'
import DetailHeader from '@/components/DetailHeader'
export default {
  name: 'Detail',
  components: { DetailHeader, Banner }
}
</script>

<style lang="stylus" scoped>
  .h
    height : 5000px
</style>
