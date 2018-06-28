<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'cityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~styles/stylus/varible.styl'
  .header
    position :relative
    line-height :$headerHeight
    height :$headerHeight
    background :$bgColor
    font-size :.32rem
    color :#fff
    text-align :center
    overflow :hidden
    .header-back
      position :absolute
      width :.64rem
      color :#fff
      font-size :.32rem
      top:0
      left:0
      text-align :center
</style>
