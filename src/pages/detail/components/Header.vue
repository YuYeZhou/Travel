<template>
  <div>
    <router-link to="/" tag="div" class="header-abs" v-show="showAbs">
      <div class="iconfont header-abs-back">&#xe624;</div>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      景点详情
      <router-link to="/">
        <div class="iconfont header-fixed-back">&#xe624;</div>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  mounted () {
    window.addEventListener('scroll', this.handleScroll)
  },
  destroyed () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/stylus/varible.styl'
  .header-abs
    position :absolute
    top :.2rem
    left :.2rem
    height :.8rem
    width :.8rem
    line-height :.8rem
    border-radius :.4rem
    text-align :center
    background :rgba(0, 0, 0, .8)
    .header-abs-back
      color :#fff
  .header-fixed
    z-index :2
    position :fixed
    top :0
    left :0
    right :0
    line-height :$headerHeight
    height :$headerHeight
    background :$bgColor
    font-size :.32rem
    color :#fff
    text-align :center
    overflow :hidden
    .header-fixed-back
      position :absolute
      width :.64rem
      color :#fff
      font-size :.32rem
      top:0
      left:0
      text-align :center
</style>
