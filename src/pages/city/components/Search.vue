<template>
  <div class="search">
    <input class="search-input" type="text" placeholder="输入城市名或拼音">
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/stylus/varible.styl'
  .search
    height :.72rem
    background :$bgColor
    padding :0 .1rem
    .search-input
      box-sizing :border-box
      width :100%
      line-height :.62rem
      height :.62rem
      text-align :center
      color :#666
      padding :0 .1rem
      border-radius :.06rem
</style>
