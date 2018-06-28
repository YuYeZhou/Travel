<template>
  <ul class="list">
    <li class="item" v-for="(word, key) of cities" :key="key">{{key}}</li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/stylus/varible.styl'
  .list
    display :flex;
    flex-direction :column
    justify-content :center
    position :absolute
    top :1.58rem
    bottom 0
    right 0
    width :.4rem
    .item
      color :$bgColor
      line-height :.4rem
      text-align :center
</style>
