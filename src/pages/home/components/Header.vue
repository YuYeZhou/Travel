<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input" @click="handleClick">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <span class="iconfont arrow-icon">&#xe771;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  methods: {
    handleClick () {
      this.$router.push('/city')
    }
  },
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/stylus/varible.styl';
  .header
    display :flex
    line-height :$headerHeight
    background-color :$bgColor
    color :#fff
    .header-left
      width :.64rem
      float :left
      .back-icon
        text-align :center
        font-size :.32rem
    .header-input
      flex :1
      height :.64rem
      border-radius :.1rem
      background-color :#fff
      margin-top :.12rem
      margin-left :.2rem
      line-height :.64rem
      color :#ccc
      padding-left :.2rem
    .header-right
      float :right
      min-width :1.04rem
      padding :0 .1rem
      text-align :center
      color :#fff
      .arrow-icon
        font-size :.24rem
        margin-left :-.04rem
</style>
