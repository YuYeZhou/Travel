<template>
  <div class="list"  ref="wrapper">
    <div>
      <div class="aera">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
        </div>
      </div>
      <div class="aera">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
        </div>
      </div>
      <div class="aera">
        <div class="title border-topbottom">A</div>
          <div class="item-list">
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
        </div>
        <div class="title border-topbottom">A</div>
          <div class="item-list">
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
        </div>
        <div class="title border-topbottom">A</div>
          <div class="item-list">
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
        </div>
        <div class="title border-topbottom">A</div>
          <div class="item-list">
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
        </div>
        <div class="title border-topbottom">A</div>
          <div class="item-list">
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
            <div class="item border-bottom">阿克苏</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/stylus/mixins.styl'
  .border-topbottom
    &:before
      border-color :#ccc
    &:after
      border-color :#ccc
  .border-bottom
    &:before
      border-color :#ccc
  .list
    overflow :hidden
    position :absolute
    top :1.58rem
    left 0
    right 0
    bottom 0
    .title
      background :#eee
      padding-left :.2rem
      line-height :.54rem
      color :#666
      font-size :.26rem
    .button-list
      padding :.1rem .6rem .1rem .1rem
      overflow :hidden
      .button-wrapper
        float :left
        width :33.33%
        .button
          border-radius :.06rem
          padding .1rem
          margin :.1rem
          text-align :center
          border :.02rem solid #ccc
    .item-list
      line-height :.76rem
      padding-left :.2rem
      color :#666
</style>
